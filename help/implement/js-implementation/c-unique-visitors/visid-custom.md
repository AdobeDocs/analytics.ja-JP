---
description: s.visitorID 変数を設定して訪問者を識別するためのカスタム方法を実装できます。
keywords: Analytics の導入
seo-description: s.visitorID 変数を設定して訪問者を識別するためのカスタム方法を実装できます。
seo-title: カスタム訪問者 ID
solution: Analytics
title: カスタム訪問者 ID
topic: 開発者と導入
uuid: 49881e27-0418-4ecf- a092- dcc3db923f40
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# カスタム訪問者 ID

s.visitorID 変数を設定して訪問者を識別するためのカスタム方法を実装できます。

カスタム訪問者 ID は、訪問者を固有の方法で識別するサイトで使用できます。例えば、ユーザーがユーザー名とパスワードを使用して Web サイトにログインする際に生成される ID は、カスタム訪問者 ID です。

ユーザーの[!UICONTROL 訪問者 ID] を取得および管理できる場合は、次の方法を使用して ID を設定できます。

| メソッド | 説明 |
|---|---|
| [s.visitorID](/help/implement/js-implementation/c-variables/page-variables.md) 変数 | ブラウザーで JavaScript が使用されている場合または他の AppMeasurement ライブラリを使用している場合は、訪問者 ID をデータ収集変数に設定できます。 |
| イメージリクエスト上のクエリ文字列パラメーター | これにより、ハードコードされたイメージリクエスト上の [!UICONTROL vid クエリ文字列]パラメーターを使用して、[!UICONTROL 訪問者 ID] をアドビに送信できます。 |
| Data Insertion API | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers. |
| URL の書き直しおよび VISTA | 一部の導入アーキテクチャでは、cookie を設定できない場合に URL の書き直しによってセッションの状態を維持する機能をサポートしています。このような場合、アドビのエンジニアリングサービスで [!DNL VISTA] ルールを導入できます。このルールでは、ページの URL 内のセッション値を検索し、整形して、[!UICONTROL visid] の各値に配置します。 |
>[!CAUTION]
>**カスタム訪問者IDは、精度が高い/一意**&#x200B;である必要があります。カスタム訪問者IDの無効な実装によって、誤ったデータやレポートのパフォーマンスが低下する可能性があります。カスタム訪問者IDが一意または詳細でない場合、または文字列"NULL"や"0"などの一般的なデフォルト値に設定されている場合、多数の異なる訪問者からのヒットは、Adobe Analyticsによって単一の訪問者として表示されます。この状況では不正確なデータが得られ、訪問者数が少なすぎて、その訪問者に対してセグメントが正しく機能しません。さらに詳細なカスタム訪問者IDを使用すると、Analyticsレポートクラスターのノード間でデータが正しく伝播されなくなります。この状況では、1つのノードが過負荷になり、レポートリクエストをタイムリーに処理できません。最終的に、レポートスイートのすべてのレポートは失敗します。<br>Analyticsが多くの場合、不均衡のデータを処理する可能性があるので、カスタム訪問者IDの実装は、レポートパフォーマンスにすぐには影響しない可能性があります。ただし、カスタム訪問者IDの値が不適切に実装されると、影響を受けるレポートスイートの処理を無効にするためにAnalyticsが必要となる点に問題が生じる可能性があります。</br><br>実装者は、単一のカスタム訪問者ID値にレポートスイートのトラフィックの1%を超えないようにするガイドラインに従う必要があります。Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>
