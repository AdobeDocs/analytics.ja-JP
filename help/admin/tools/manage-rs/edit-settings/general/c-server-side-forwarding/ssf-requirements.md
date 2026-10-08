---
description: サーバーサイド転送を実装するには、CX Enterprise ソリューション、サービス、コードの要件を満たす必要があります。 これらの要件には、コードバージョンの確認方法と最新のコードライブラリの取得先に関する手順も含まれています。
solution: Analytics
title: サーバー側転送の要件
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: 'https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 43%
---
# サーバー側転送の要件

サーバーサイド転送を実装するには、CX Enterprise ソリューション、サービス、コードの要件を満たす必要があります。 これらの要件には、コードバージョンの確認方法と最新のコードライブラリの取得先に関する手順も含まれています。

## ソリューションの要件

サーバー側転送は、[Analytics](https://www.adobe.com/jp/data-analytics-cloud/analytics.html)、[Audience Manager](https://www.adobe.com/jp/analytics/audience-manager.html) および [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=ja) に対応しています。

## サービスの要件

サーバー側転送には、[ID サービス](https://experienceleague.adobe.com/ja/docs/id-service/using/home)が必要です。 Identity Serviceは、CX Enterprise内のあらゆるソリューションをまたいでサイト訪問者を識別するユニバーサル IDを提供します。 サーバーサイド転送が動作するためには、事前に ID サービスを実装する必要があります。

## コードバージョン

サーバーサイド転送には、以下に示すコードライブラリのバージョン 1.5 （またはそれ以降）が必要です。 ベストプラクティスとして、これらの必須の最小値ではなく、最新バージョンを使用することをお勧めします。

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### コードライブラリのバージョンの確認

AppMeasurement および訪問者 API コードのバージョン番号は、ブラウザーによって発行された HTTP リクエストを監視するすべてのツールで表示できます。 `AppMeasurement_Module_AudienceManagement.js` の場合は、バージョン ID が含まれず、この値は返されません。 `AppMeasurement.js` および `VisitorAPI.js` コードのバージョン ID の例を以下に示します。

* `AppMeasurement.js`: バージョンは、応答タイプ （`/b/ss/examplersid/1/JS-X.X.X/s234234238479`など）の後のリクエスト URLに表示されます。 デコード要求を行う[&#x200B; デバッグツール &#x200B;](/help/implement/validate/debugging-tools.md)は別のラベルを使用できますが、値は常にパターン `JS-X.X.X`に従います。ここで、`X`はバージョン番号です。
* `VisitorAPI.js`：`d_visid_ver` パラメーターを探します。 訪問者 ID サービスが `d_visid_ver: 1.5.5` という形式で表示されます。 バージョン 1.5.2より古い訪問者API コードには、バージョン番号が含まれていませんでした。 監視結果にバージョン番号が返されない場合は、古いコードライブラリを使用している可能性があります（アップグレードが必要です）。
