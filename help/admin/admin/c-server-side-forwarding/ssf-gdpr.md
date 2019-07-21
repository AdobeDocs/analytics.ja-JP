---
description: 'null'
seo-description: 'null'
seo-title: GGPR/epリブ通信準拠およびサーバー側転送
title: GGPR/epリブ通信準拠およびサーバー側転送
uuid: 1b90c567-3321-4dbd- a699-38c04e809fa4
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# GGPR/epリブ通信準拠およびサーバー側転送

ここでは、2017 年 9 月 30 日に施行された [EU Cookie コンプライアンス規定](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm)によるサーバー側転送に対する最近の機能強化について説明します。

Server-side forwarding is used to share data from Adobe Analytics to other [!DNL Experience Cloud Solutions], such as Audience Manager, in real time. サーバー側転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。

最近まで、サーバー側転送には、同意および同意前のイベント／ヒットを説明する方法がありませんでした。2018 年 11 月 1 日以降、データ管理者であるお客様（Adobe Analytics のお客様）には、同意前のデータを Adobe Analytics に限定して、AAM に転送しないようにするオプションがあります。新しい実装コンテキスト変数を使用すると、同意を受けていないヒットにフラグを設定できます。この変数を設定すると、同意を受け取るまで、これらのヒットは AAM に送信されません。

When this new context variable, `cm.ssf=1`, exists on a hit, this hit gets flagged and does not get server-side-forwarded to AAM. 反対に、この文字列がヒットにない場合、ヒットは AAM に転送されます。

サーバー側転送は双方向です。つまり、ヒットに適用されてそのヒットが AAM に転送されると、Audience Analytics は、AAM からそのヒットに関するセグメント情報を受け取り、Analytics に送り返します。結果として、Analytics から AAM にサーバー側転送されていないヒットは、AAM からのセグメント ID のリストで強化されません。したがって、AAM からセグメント ID 情報を取得しないトラフィック／ヒットのサブセットになります。

## 実装の詳細 {#section_FFA8B66085BF469FAB5365C944FE38F7}

実装方法に応じて、次の手順に従います。

| 実装方法 | 手順 |
|--- |--- |
| Adobe Experience Platform Launch | Assuming you have the Adobe Analytics extension installed, add the following context data variable definition to the custom code editor within the Action configuration of a Rule: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the `contextdata` variable to *0* for customers who consented to targeted marketing. |
| DTM | コンテキストデータ変数定義をカスタムページコードエディターに追加します。<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：ターゲットのマーケティングに顧客が同意していない場合、contextdata 変数を定義して、1 に設定します。ターゲットのマーケティングに同意した顧客については、contextdata 変数を 0 に設定します。 |
| AppMeasurement | コンテキストデータ変数定義を AppMeasurement.js ファイルに追加します。<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：ターゲットのマーケティングに顧客が同意していない場合、contextdata 変数を定義して、1 に設定します。ターゲットのマーケティングに同意した顧客については、contextdata 変数を 0 に設定します。 |

## レポート（オプション） {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Adobe Analytics を使用して、どのくらいのトラフィックが同意され、結果として AAM にサーバー側転送されているかと、どのくらいのトラフィックが同意されず、結果としてサーバー側転送されていないかを比較してレポートできます。

このタイプのレポートを設定するには、処理ルールを使用して、新しいコンテキスト変数をカスタムトラフィック変数（prop）にマッピングします。次に手順を示します。

1. （前述のように）「cm.ssf」変数を実装します。
1. [prop を有効にします。](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. 処理ルールを使用して、コンテキスト変数を prop にマッピングします。

   1. **[!UICONTROL Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL レポートスイート]** に移動し、レポートスイートを選択します。
   1. Click  **[!UICONTROL Edit Report Suite]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Processing Rules]** .
   1. 「**[!UICONTROL ルールを追加」をクリックします。]**
   1. **[!UICONTROL 「常に実行]**」で、コンテキスト変数"cm. ssf（コンテキストデータ）」で有効にしたpropの値を上書きします。
   1. 「**[!UICONTROL 保存]**」をクリックします。

