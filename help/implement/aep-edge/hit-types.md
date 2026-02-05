---
title: Adobe Analytics の Edge Network イベントタイプ
description: Adobe Analytics での Edge Network から受信したイベントの解釈方法。
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: ht
source-wordcount: '425'
ht-degree: 100%

---

# Adobe Analytics の Edge Network イベントタイプ

Adobe Analytics では、AppMeasurement で呼び出す関数に応じてヒットの処理が異なります。例えば、[`s.t`](/help/implement/vars/functions/t-method.md) と [`s.tl`](/help/implement/vars/functions/tl-method.md) では、特定のディメンションが含められるか省略されます。また、[ページビュー](/help/components/metrics/page-views.md)の増分が異なります。Adobe Experience Platform には、[`sendEvent`](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/commands/sendevent/overview) コマンドのみが含まれます。[`xdm`](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/commands/sendevent/xdm) または [`data`](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/commands/sendevent/data) ペイロード内の特定のプロパティによって、Adobe Analytics でそのデータの解釈方法が決まります。

Edge Network は、次のロジックを使用して Adobe Analytics の[ページビュー](/help/components/metrics/page-views.md)と[リンクイベント](/help/components/metrics/page-events.md)を決定します。

## `xdm` オブジェクトを使用したページビューとリンクイベント

| XDM ペイロードには次のものが含まれます。 | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL` and no `xdm.web.webInteraction.type` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `xdm.eventType = web.webpagedetails.pageViews` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `xdm.web.webInteraction.type` and (`xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL`) | ペイロードを&#x200B;**リンクイベント**&#x200B;とみなします <br/>また、`xdm.web.webPageDetails.name` と `xdm.web.webPageDetails.URL` を `null` に設定します |
| `xdm.web.webInteraction.type` and (`xdm.web.webInteraction.name` or `xdm.web.webInteraction.URL`) | ペイロードを&#x200B;**リンクイベント**&#x200B;とみなします <br/>`xdm.web.webPageDetails.name` と `xdm.web.webPageDetails.URL` が存在する場合は `null` に設定します |
| no `xdm.web.webInteraction.type` and no `xdm.web.webPageDetails.name` and no `xdm.web.webPageDetails.URL` | ペイロードをドロップし、データを無視します |

>[!TIP]
>
>ペイロード内の XDM フィールド名では大文字と小文字が区別されます（例：`webPageDetails.URL`）。`xdm.eventType` フィールドは、独自の許容値セットを持つ文字列値で、これらの値の大文字と小文字は XDM フィールド名と一致しない可能性があります。許容値について詳しくは、[XDM ExperienceEvent クラス](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/classes/experienceevent#eventType)の `eventType` フィールドを参照してください。

+++`xdm` フィールドを使用した最小限のページビュー

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++`xdm.eventType` を使用した最小限のページビュー

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++推奨フィールドを使用した最小限のリンクイベント

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## `data` オブジェクトを使用したページビューとリンクイベント

| データオブジェクトペイロードには次のものが含まれます。 | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` or `data.__adobe.analytics.pageURL` and no `data.__adobe.analytics.linkType` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `data.__adobe.analytics.linkType` and (`data.__adobe.analytics.linkName` or `data.__adobe.analytics.linkURL`) | ペイロードを&#x200B;**リンクイベント**&#x200B;とみなします <br/>また、`data.__adobe.analytics.pageName` と `data.__adobe.analytics.pageURL` を `null` に設定します |
| no `data.__adobe.analytics.linkType` and no `data.__adobe.analytics.pageName` and no `data.__adobe.analytics.pageURL` | ペイロードをドロップし、データを無視します |

+++`data` フィールドを使用した最小限のページビュー

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++`data` フィールドを使用した最小限のリンクイベント

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>`xdm` オブジェクトと `data` オブジェクトの両方を同じペイロードに含める場合、Adobe Analytics では両方のオブジェクトで各フィールドを確認します。

## A4T と意思決定関連のイベント

ページビューとリンクイベントを区別することに加えて、次のロジックにより、特定の決定イベントが A4T として分類されるか、破棄されるかが決定します。

| XDM ペイロードには次のものが含まれます。 | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` と `xdm._experience.decisioning` | ペイロードを **A4T** 呼び出しとみなします。 |
| `xdm.eventType = decisioning.propositionDisplay` and no `xdm._experience.decisioning` | ペイロードをドロップし、データを無視します |
| `xdm.eventType = decisioning.propositionInteract` and `xdm._experience.decisioning` and no `xdm.web.webInteraction.type` | ペイロードを **A4T** 呼び出しとみなします。 |
| `xdm.eventType = decisioning.propositionInteract` and no `xdm._experience.decisioning` and no `xdm.web.webInteraction.type` | ペイロードをドロップし、データを無視します。 |
| `xdm.eventType = decisioning.propositionFetch` | ペイロードをドロップし、データを無視します |

>[!TIP]
>
>次の `eventType` 値は非推奨（廃止予定）です。これらの値は、現在の値と同じようにロジックに影響を与えます。
>
>* イベントタイプ `display` は非推奨（廃止予定）です。 代わりに、`decisioning.propositionDisplay` を使用してください。
>* イベントタイプ `click` は非推奨（廃止予定）です。代わりに、`decisioning.propositionInteract` を使用してください。
>* イベントタイプ `personalization.request` は非推奨（廃止予定）です。代わりに、`decisioning.propositionFetch` を使用してください。

+++最小限の A4T 表示

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++最小限の A4T インタラクション

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

詳しくは、[Adobe Analytics ExperienceEvent フル拡張スキーマフィールドグループ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)を参照してください。
