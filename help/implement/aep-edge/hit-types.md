---
title: Adobe AnalyticsのEdge Network イベントタイプ
description: Edge Networkから受信したイベントをAdobe Analyticsがどのように解釈するか。
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 20%

---

# Adobe AnalyticsのEdge Network イベントタイプ

Adobe Analyticsでは、AppMeasurementで呼び出す関数に応じてヒットの処理が異なります。 例えば、[`s.t`](/help/implement/vars/functions/t-method.md) と [`s.tl`](/help/implement/vars/functions/tl-method.md) は、特定のディメンションを含めるか除外し、増分 [&#x200B; ページビュー &#x200B;](/help/components/metrics/page-views.md) を異なる方法で行います。 Adobe Experience Platformには、[`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/overview) コマンドのみが含まれます。 [`xdm`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/xdm) または [`data`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/data) ペイロード内の特定のプロパティによって、そのデータがAdobe Analyticsでどのように解釈されるかが決まります。

Edge Networkでは、次のロジックを使用して、Adobe Analytics[&#x200B; ページビュー &#x200B;](/help/components/metrics/page-views.md) および [&#x200B; リンクイベント &#x200B;](/help/components/metrics/page-events.md) を判断します。

## `xdm` オブジェクトを使用したページビューおよびリンクイベント

| XDM ペイロードには次のものが含まれます。 | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL` and no `xdm.web.webInteraction.type` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `xdm.eventType = web.webpagedetails.pageViews` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `xdm.web.webInteraction.type` and (`xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL`) | ペイロードを **リンクイベント** とみなします <br/>`xdm.web.webPageDetails.name` および `xdm.web.webPageDetails.URL` も `null` に設定します |
| `xdm.web.webInteraction.type` and (`xdm.web.webInteraction.name` or `xdm.web.webInteraction.URL`) | ペイロードを **リンクイベント** とみなします <br/> また、`xdm.web.webPageDetails.name` と `xdm.web.webPageDetails.URL` を `null` に設定します（存在する場合） |
| `xdm.web.webInteraction.type` も `xdm.web.webPageDetails.name` も `xdm.web.webPageDetails.URL` もない | ペイロードをドロップし、データを無視します |

>[!TIP]
>
>ペイロード内の XDM フィールド名では大文字と小文字が区別されます（例：`webPageDetails.URL`）。 `xdm.eventType` フィールドは、受け入れ可能な独自の値セットを持つ文字列値であり、これらの値の大文字と小文字は、XDM フィールド名と一致しない場合があります。 使用できる値については、`eventType`XDM ExperienceEvent クラス [&#x200B; の &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent#eventType) フィールドを参照してください。

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

+++推奨フィールドを使用した最小リンクイベント

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

## `data` オブジェクトを使用したページビューおよびリンクイベント

| データオブジェクトペイロードに次を含む… | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` or `data.__adobe.analytics.pageURL` and no `data.__adobe.analytics.linkType` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `data.__adobe.analytics.linkType` and (`data.__adobe.analytics.linkName` or `data.__adobe.analytics.linkURL`) | ペイロードを **リンクイベント** とみなします <br/>`data.__adobe.analytics.pageName` および `data.__adobe.analytics.pageURL` も `null` に設定します |
| `data.__adobe.analytics.linkType` も `data.__adobe.analytics.pageName` も `data.__adobe.analytics.pageURL` もない | ペイロードをドロップし、データを無視します |

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

+++`data` フィールドを使用した最小リンクイベント

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
>`xdm` オブジェクトと `data` オブジェクトの両方を同じペイロードに含める場合、Adobe Analyticsは両方のオブジェクトで各フィールドを確認します。

## A4T と意思決定関連のイベント

次のロジックは、ページビューとリンクイベントの違いに加えて、特定の決定イベントを A4T として分類するか破棄するかを決定します。

| XDM ペイロードには次のものが含まれます。 | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` と `xdm._experience.decisioning` | は、ペイロードを **A4T** 呼び出しとみなします。 |
| `xdm.eventType = decisioning.propositionDisplay` と `xdm._experience.decisioning` なし | ペイロードをドロップし、データを無視します |
| `xdm.eventType = decisioning.propositionInteract` と `xdm._experience.decisioning` と `xdm.web.webInteraction.type` なし | は、ペイロードを **A4T** 呼び出しとみなします。 |
| `xdm.eventType = decisioning.propositionInteract` と `xdm._experience.decisioning` と `xdm.web.webInteraction.type` | ペイロードをドロップし、データを無視します。 |
| `xdm.eventType = decisioning.propositionFetch` | ペイロードをドロップし、データを無視します |

>[!TIP]
>
>次の `eventType` 値は非推奨（廃止予定）です。 これらの値は、現在の値と同じようにロジックに影響を与えます。
>
>* イベントタイプ `display` は非推奨（廃止予定）です。 代わりに、`decisioning.propositionDisplay` を使用してください。
>* イベントタイプ `click` は非推奨（廃止予定）です。 代わりに、`decisioning.propositionInteract` を使用してください。
>* イベントタイプ `personalization.request` は非推奨（廃止予定）です。 代わりに、`decisioning.propositionFetch` を使用してください。

+++A4T の最小限の表示

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

+++A4T のインタラクションの最小化

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

詳しくは、[Adobe Analytics ExperienceEvent フル拡張スキーマフィールドグループ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)を参照してください。
