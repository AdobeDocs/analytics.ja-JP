---
description: EU cookieコンプライアンス規則によって促された、サーバ側転送の改良点を説明します。
title: GDPR／ePrivacy コンプライアンスおよびサーバー側転送
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
translation-type: tm+mt
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 90%

---

# GDPR／ePrivacy コンプライアンスおよびサーバー側転送

この節では、2017年9月30日に発効した[EU cookieコンプライアンス規則](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm)によるサーバー側転送の強化について説明します。

サーバー側転送は、Adobe Analytics から他の [!DNL Experience Cloud Solutions] ソリューション（Audience Manager など）にリアルタイムでデータを共有するために使用されます。サーバー側転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。

以前は、サーバー側転送では、同意と事前同意のイベント/ヒットを区別する方法がありませんでした。 2018 年 11 月 1 日以降、データ管理者であるお客様（Adobe Analytics のお客様）には、同意前のデータを Adobe Analytics に限定して、AAM に転送しないようにするオプションがあります。新しい実装コンテキスト変数を使用すると、同意を受けていないヒットにフラグを設定できます。この変数を設定すると、同意を受け取るまで、これらのヒットは AAM に送信されません。

この新しいコンテキスト変数「`cm.ssf=1`」がヒットに存在する場合、このヒットにはフラグが設定され、AAM へのサーバー側転送はおこなわれません。反対に、この文字列がヒットにない場合、ヒットは AAM に転送されます。

サーバー側転送は双方向です。つまり、ヒットに適用されてそのヒットが AAM に転送されると、Audience Analytics は、AAM からそのヒットに関するセグメント情報を受け取り、Analytics に送り返します。結果として、Analytics から AAM にサーバー側転送されていないヒットは、AAM からのセグメント ID のリストで強化されません。したがって、AAM からセグメント ID 情報を取得しないトラフィック／ヒットのサブセットになります。

## 実装の詳細 {#section_FFA8B66085BF469FAB5365C944FE38F7}

実装方法に応じて、次の手順に従います。

| 実装方法 | 手順 |
|--- |--- |
| Adobe Experience Platform Launch | Adobe Analytics 拡張機能がインストールされている場合は、ルールのアクション設定内のカスタムコードエディターに次のコンテキストデータ変数定義を追加します。<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注： 顧客がターゲットのマーケティングに同意しない場合は、contextdata 変数を定義し、1 に設定します。ターゲットのマーケティングに同意した顧客については、`contextdata` 変数を *0* に設定します。 |
| AppMeasurement | コンテキストデータ変数定義を AppMeasurement.js ファイルに追加します。            <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注： 顧客がターゲットのマーケティングに同意しない場合は、contextdata 変数を定義し、1 に設定します。ターゲットのマーケティングに同意した顧客については、contextdata 変数を 0 に設定します。 |

## レポート（オプション） {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Adobe Analytics を使用して、どのくらいのトラフィックが同意され、結果として AAM にサーバー側転送されているかと、どのくらいのトラフィックが同意されず、結果としてサーバー側転送されていないかを比較してレポートできます。

このタイプのレポートを設定するには、処理ルールを使用して、新しいコンテキスト変数をカスタムトラフィック変数（prop）にマッピングします。次に手順を示します。

1. （前述のように）「cm.ssf」変数を実装します。
1. [prop を有効にします。](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. 処理ルールを使用して、コンテキスト変数を prop にマッピングします。

   1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;に移動し、レポートスイートを選択します。
   1. **[!UICONTROL レポートスイートを編集]**／**[!UICONTROL 一般]**／**[!UICONTROL 処理ルール]**&#x200B;をクリックします。
   1. 「**[!UICONTROL ルールを追加]**」をクリックします。
   1. 「**[!UICONTROL 常に実行]**」で、入力した prop の値をコンテキスト変数「cm.ssf(Context Data)」で上書きします。
   1. 「**[!UICONTROL 保存]**」をクリックします。
