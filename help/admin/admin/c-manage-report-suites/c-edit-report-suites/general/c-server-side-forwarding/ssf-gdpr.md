---
description: EU Cookie コンプライアンス規則によって促されたサーバーサイド転送の機能強化について説明します。
title: GDPR／ePrivacy コンプライアンスおよびサーバー側転送
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 55%

---

# GDPR／ePrivacy コンプライアンスおよびサーバー側転送

ここでは、2017年9月30日（PT）に施行された [EU Cookie コンプライアンス規定](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies)によるサーバーサイド転送に対する機能強化について説明します。

サーバー側転送は、Adobe Analytics から他の [!DNL Experience Cloud Solutions] ソリューション（Audience Manager など）にリアルタイムでデータを共有するために使用されます。サーバーサイド転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。

これまで、サーバーサイド転送には、同意後と同意前のイベント／ヒットを区別する方法がありませんでした。2018 年 11 月 1 日（PT）をもって、データ管理者（Adobe Analyticsのお客様）は、同意前のデータをAdobe Analyticsに限定し、Adobe Audience Managerに転送しないようにするオプションを持ちます。 新しい実装コンテキスト変数を使用すると、同意を受けていないヒットにフラグを設定できます。変数を設定すると、これらのヒットが、同意が得られるまでAdobe Audience Managerに送信されなくなります。

この新しいコンテキスト変数 `cm.ssf=1` がヒットに存在する場合、このヒットはフラグ付けされ、Adobe Audience Managerにサーバーサイド転送されません。 逆に、この文字列がヒットで表示されない場合、ヒットはAdobe Audience Managerに転送されます。

サーバーサイド転送は双方向です。つまり、ヒットに適用され、そのヒットがAdobe Audience Managerに転送されると、Audience Analyticsはヒットのセグメント情報をAdobe Audience Managerから受け取り、Analytics に返します。 その結果、Analytics からAdobe Audience Managerにサーバーサイド転送されないヒットは、Adobe Audience Managerのセグメント ID のリストでエンリッチメントされません。 したがって、Adobe Audience Managerからセグメント ID 情報を取得しないトラフィック/ヒットのサブセットが存在します。

## 実装の詳細 {#section_FFA8B66085BF469FAB5365C944FE38F7}

実装方法に応じて、次の手順に従います。

| 実装方法 | 手順 |
|--- |--- |
| Adobe Experience Platform のタグ | Adobe Analytics 拡張機能がインストールされている場合は、ルールのアクション設定内のカスタムコードエディターに次のコンテキストデータ変数定義を追加します。<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>メモ： 顧客がターゲットマーケティングに同意しない場合は、contextdata 変数を定義し、1 に設定します。ターゲットマーケティングに同意した顧客については、`contextdata` 変数を *0* に設定します。 |
| AppMeasurement | コンテキストデータ変数の定義をAppMeasurement.js ファイルに追加します。<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/> メモ：ターゲットマーケティングに同意しない場合は、contextdata 変数を定義し、1 に設定します。 ターゲットマーケティングに同意した顧客については、contextdata 変数を 0 に設定します。 |

## レポート（任意） {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Adobe Analyticsを使用すると、同意に基づいたトラフィックの割合をレポートできます。その結果、サーバーサイド転送されたトラフィックと、同意に基づかずAdobe Audience Managerに転送されていないトラフィックの割合を比較できます。

このタイプのレポートを設定するには、処理ルールを使用して、新しいコンテキスト変数をカスタムトラフィック変数（prop）にマッピングします。次に手順を示します。

1. （前述のように）「cm.ssf」変数を実装します。
1. [prop を有効にします。](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
1. 処理ルールを使用して、コンテキスト変数を prop にマッピングします。

   1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;に移動し、レポートスイートを選択します。
   1. **[!UICONTROL レポートスイートを編集]**／**[!UICONTROL 一般]**／**[!UICONTROL 処理ルール]**&#x200B;をクリックします。
   1. 「**[!UICONTROL ルールを追加]**」をクリックします。
   1. 「**[!UICONTROL 常に実行]**」で、入力した prop の値をコンテキスト変数「cm.ssf(Context Data)」で上書きします。
   1. 「**[!UICONTROL 保存]**」をクリックします。
