---
description: EU Cookie コンプライアンス規則によって促されたサーバーサイド転送の機能強化について説明します。
title: GDPR／ePrivacy コンプライアンスおよびサーバー側転送
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
TQID: 'https://experienceleague.adobe.com/MH--f5MxzLFOkDV8B-JzqMULLbY1ota6efoJ8T1ne58'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c354699e-6555-4397-8706-1a9a89984069
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 588
ht-degree: 42%

---

# GDPR／ePrivacy コンプライアンスおよびサーバー側転送

ここでは、2017年9月30日（PT）に施行された [EU Cookie コンプライアンス規定](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies)によるサーバーサイド転送に対する機能強化について説明します。

サーバーサイド転送は、Adobe Analyticsのデータを、Audience ManagerなどのCX Enterprise ソリューションとリアルタイムで共有するために使用されます。 サーバーサイド転送を有効にすると、Analyticsはデータを他のCX Enterprise ソリューションにプッシュし、それらのソリューションではデータ収集プロセス中にデータをAnalyticsにプッシュできます。

これまで、サーバーサイド転送には、同意後と同意前のイベント／ヒットを区別する方法がありませんでした。 2018年11月1日現在、お客様（Adobe Analyticsのお客様）は、事前同意データをAdobe Analyticsに制限し、Adobe Audience Managerへの転送を禁止するオプションを選択できます。 新しい実装コンテキスト変数を使用すると、同意を受けていないヒットにフラグを設定できます。 この変数を設定すると、同意を受け取るまで、これらのヒットは Adobe Audience Manager に送信されません。

この新しいコンテキスト変数`cm.ssf=1`がヒットに存在する場合、このヒットにフラグが付けられ、Adobe Audience Managerにサーバーサイド転送されません。 逆に、この文字列がヒットに表示されない場合、ヒットはAdobe Audience Managerに転送されます。

サーバーサイド転送は双方向です。つまり、ヒットに適用され、ヒットがAdobe Audience Managerに転送されると、Audience Analyticsはそのヒットに関するセグメント情報をAdobe Audience Managerから受け取り、Analyticsに送り返します。 そのため、AnalyticsからAdobe Audience Managerにサーバーサイドで転送されないヒットは、Adobe Audience Managerのセグメント IDのリストでエンリッチされません。 したがって、Adobe Audience Managerからセグメント ID情報を取得しないトラフィック/ヒットのサブセットが存在します。

## 実装の詳細 {#section_FFA8B66085BF469FAB5365C944FE38F7}

実装方法に応じて、次の手順に従います。

| 実装方法 | 手順 |
|--- |--- |
| Adobe Experience Platform のタグ | Adobe Analytics 拡張機能がインストールされている場合は、ルールのアクション設定内のカスタムコードエディターに次のコンテキストデータ変数定義を追加します。<br/>`s.contextData['cm.ssf'] = '1'` <br/>メモ： 顧客がターゲットマーケティングに同意しない場合は、contextdata 変数を定義し、1 に設定します。 ターゲットマーケティングに同意した顧客については、`contextdata` 変数を *0* に設定します。 |
| AppMeasurement | AppMeasurement.js ファイルにコンテキストデータ変数定義を追加します：<br/>`s.contextData['cm.ssf'] = '1'` <br/>注意：顧客がターゲットマーケティングに同意しない場合は、コンテキストデータ変数を定義し、1に設定します。 ターゲットマーケティングに同意した顧客については、contextdata 変数を 0 に設定します。 |

## レポート（任意） {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Adobe Analyticsを使用すると、同意に基づくトラフィックの量と、その結果サーバーサイドで転送されたトラフィックと、同意に基づかないトラフィックおよびAdobe Audience Managerに転送されていないトラフィックの量をレポートできます。

このタイプのレポートを設定するには、処理ルールを使用して、新しいコンテキスト変数をカスタムトラフィック変数（prop）にマッピングします。 これを行うには

1. （前述のように）「cm.ssf」変数を実装します。
1. [propを有効にします。](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
1. 処理ルールを使用して、コンテキスト変数を prop にマッピングします。

   1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;に移動し、レポートスイートを選択します。
   1. **[!UICONTROL レポートスイートを編集]**／**[!UICONTROL 一般]**／**[!UICONTROL 処理ルール]**&#x200B;をクリックします。
   1. 「**[!UICONTROL ルールを追加]**」をクリックします。
   1. 「**[!UICONTROL 常に実行]**」で、入力した prop の値をコンテキスト変数「cm.ssf(Context Data)」で上書きします。
   1. 「**[!UICONTROL 保存]**」をクリックします。
