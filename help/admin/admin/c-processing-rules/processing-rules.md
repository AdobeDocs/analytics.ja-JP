---
description: 処理ルールはデータ収集をシンプル化し、レポーティングに送信されるコンテンツを管理します。
seo-description: 処理ルールはデータ収集をシンプル化し、レポーティングに送信されるコンテンツを管理します。
seo-title: 処理ルールの概要
solution: Analytics
subtopic: 処理ルール
title: 処理ルールの概要
topic: 管理ツール
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 処理ルールの概要

処理ルールはデータ収集をシンプル化し、レポーティングに送信されるコンテンツを管理します。処理ルールは、以下に対するインターフェイスを提供することにより、IT グループおよび Web 開発者とのやり取りの単純化に役立ちます。

* 製品の概要ページでイベントを設定する
* クエリ文字列パラメーターでキャンペーンを入力する
* レポートを容易にするために、prop でカテゴリとページ名を連結する
* eVar を prop にコピーし、パスを確認する
* スペルを間違えたサイトセクションのクリーンアップ
* クエリ文字列から eVar に内部検索用語またはキャンペーン ID を取り込む

>[!VIDEO](https://tv.adobe.com/embed/1181/16506/)

処理ルールを使用する理由について、処理ルールの概要と Adobe Summit のトレーニングを&#x200B;*ご覧ください。*

## 処理ルール使用の承認を得る {#section_8A4846688050453784DAE4D89355169A}

2017 年 4 月 21 日以前は、すべてのユーザー（管理者を含む）が試験に合格し、処理ルールを使用する権限をアドビカスタマーケアから受け取る必要がありました。

現在は、管理者には処理ルールを使用する権限が&#x200B;**デフォルトで**&#x200B;与えられています。試験を受ける必要はなくなりました。また、管理者は、管理ツールインターフェイスを使用してこの権限を非管理者に付与できます。その方法を次に示します。

1. まだ完了していなければ、処理ルールを使用する権限を持つべき非管理者のみで構成される   [グループを作成](../../../admin/user-management2/c-user-groups/groups.md)します。
1. [Add the non-administrators to that group.](../../../admin/user-management2/c-user-management/t-add-user-to-group.md)
1. Then go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL[group name]]** &gt; **[!UICONTROL Edit]** &gt; **[!UICONTROL Report Access]** &gt; **[!UICONTROL Report Suite Tools]** &gt; **[!UICONTROL Customize]** &gt; **[!UICONTROL Report Suite Management]**.
1. Check the box next to [!UICONTROL Processing Rules] and click **[!UICONTROL OK]**.

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>処理ルールはAnalyticsデータに永続的な影響を与えるので、処理ルール管理者はAdobe Analyticsで認定トレーニングを受け、レポートスイート（標準Webサイト、モバイルサイト、モバイルアプリ、Data Insertion APIなど）のすべてのデータソースに精通することを強くお勧めします。 様々なプラットフォームで入力されるコンテキストデータ変数と標準変数に関する知識は、データの予期しない削除や変更を防ぐのに役立ちます。

## コンテキストデータを使用したデータ収集の単純化 {#section_09EEA03612D24C15839631AA9E9668D8}

コンテキストデータ変数は、処理ルールにのみ使用できる新しいタイプの変数です。コンテキストデータを使用するには、キー／値データペアを送信し、処理ルールを使用して標準的な Analytics 変数にこれらの値を取り込みます。これによって、プログラマーは prop や eVar に含めるべき値を正確に理解する必要がなくなります。

![](assets/evar-context-map.png)

実装のヘルプの[コンテキストデータ変数](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html)を参照してください。

## 処理ルールを使用したヒットデータの変換とイベントのトリガー {#section_8284E72E999244E091CD7FB1A22342B6}

処理ルールでは、受け入れる値を監視し、よくある入力ミスを変換したり、レポートされたデータに基づいてイベントを設定したりできます。prop は eVar にコピーでき、レポートで値を連結でき、イベントを設定できます。

## レポートでのコンテキストデータ変数の使用 {#section_BD098BC503024A0B8703596628071134}

定義したコンテキストデータ変数をレポートで使用するには、eVar などの変数にコピーする必要があります。

詳しくは、 here and here.[](../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7)[](../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md#concept_359B4E165ED442938A8EB6A55A725682)
