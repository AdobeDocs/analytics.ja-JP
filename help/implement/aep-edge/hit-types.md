---
title: Adobe AnalyticsのEdge Network イベントタイプ
description: Edge Networkから受信したイベントをAdobe Analyticsがどのように解釈するか。
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 6e500007e10086c0ff8108856a3563d7702f1130
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 25%

---

# Adobe AnalyticsのEdge Network イベントタイプ

Adobe Analyticsでは、AppMeasurementで呼び出す関数に応じてヒットの処理が異なります。 例えば、[`s.t`](/help/implement/vars/functions/t-method.md) と [`s.tl`](/help/implement/vars/functions/tl-method.md) は、特定のディメンションを含めるか除外し、ページビューを増分する方法が異なります。 Adobe Experience Platformには、`sendEvent` コマンドのみが含まれます。 `xdm` ペイロード内の特定のプロパティによって、そのデータがAdobe Analyticsでどのように解釈されるかが決まります。

Edge Networkでは、次のロジックを使用して、Adobe Analyticsのページビューとリンクイベントを判断します。

| XDM ペイロードには次のものが含まれます。 | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL` and no `xdm.web.webInteraction.type` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `xdm.eventType = web.webPageDetails.pageViews` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `xdm.web.webInteraction.type` and (`xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.url`) | ペイロードを **リンクイベント** とみなします <br/>`xdm.web.webPageDetails.name` および `xdm.web.webPageDetails.URL` も `null` に設定します |
| `xdm.web.webInteraction.type` も `xdm.webPageDetails.name` も `xdm.web.webPageDetails.URL` もない | ペイロードをドロップし、データを無視します |

| データオブジェクトペイロードに次を含む… | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` or `data.__adobe.analytics.pageURL` and no `data.__adobe.analytics.linkType` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `data.__adobe.analytics.linkType` and (`data.__adobe.analytics.linkName` or `data.__adobe.analytics.linkURL`) | ペイロードを **リンクイベント** とみなします <br/>`data.__adobe.analytics.pageName` および `data.__adobe.analytics.pageURL` も `null` に設定します |
| `data.__adobe.analytics.linkType` も `data.__adobe.analytics.pageName` も `data.__adobe.analytics.pageURL` もない | ペイロードをドロップし、データを無視します |

>[!NOTE]
>
>`xdm` オブジェクトと `data` オブジェクトの両方を同じペイロードに含める場合、Adobe Analyticsは両方のオブジェクトで各フィールドを確認します。

ページビュー数とリンククリック数の違いに加えて、特定のイベントを A4T として分類するか破棄するかを決定する次のロジックが用意されています。

| XDM ペイロードには次のものが含まれます。 | Adobe Analytics... |
|---|---|
| `xdm.eventType = display`、<br/>`xdm.eventType = decisioning.propositionDisplay`、<br/>`xdm.eventType = personalization.request`、<br/>`xdm.eventType = decisioning.propositionFetch`、`xdm._experience.decisioning` | は、ペイロードを **A4T** 呼び出しとみなします。 |
| `xdm.eventType = display`、<br/>`xdm.eventType = decisioning.propositionDisplay`、<br/>`xdm.eventType = personalization.request`、<br/>`xdm.eventType = decisioning.propositionFetch` で `xdm._experience.decisioning` なし | ペイロードをドロップし、データを無視します |
| `xdm.eventType = click` または `xdm.eventType = decisioning.propositionInteract` と `xdm._experience.decisioning` で `web.webInteraction.type` なし | は、ペイロードを **A4T** 呼び出しとみなします。 |
| `xdm.eventType = click` または `xdm.eventType = decisioning.propositionInteract`、`xdm._experience.decisioning` および `web.webInteraction.type` なし | ペイロードをドロップし、データを無視します。 |

詳しくは、[Adobe Analytics ExperienceEvent フル拡張スキーマフィールドグループ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)を参照してください。
