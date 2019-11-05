---
description: サーバー側転送を実装するには、次の Experience Cloud ソリューション、サービス、コードの要件を満たす必要があります。この要件の説明には、コードのバージョンを確認するための手順と最新のコードライブラリの入手先も含まれています。
seo-description: サーバー側転送を実装するには、次の Experience Cloud ソリューション、サービス、コードの要件を満たす必要があります。この要件の説明には、コードのバージョンを確認するための手順と最新のコードライブラリの入手先も含まれています。
seo-title: サーバー側転送の要件
solution: Audience Manager
title: サーバー側転送の要件
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# サーバー側転送の要件

サーバー側転送を実装するには、次の Experience Cloud ソリューション、サービス、コードの要件を満たす必要があります。この要件の説明には、コードのバージョンを確認するための手順と最新のコードライブラリの入手先も含まれています。

## ソリューションの要件

サーバー側転送は、[Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html)、[Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) および [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) に対応しています。

## サービスの要件

サーバー側転送には、IDサービスが [必要です](https://marketing.adobe.com/resources/help/en_US/mcvid/)。 IDサービスは、Experience cloudのすべてのソリューションでサイト訪問者を識別するユニバーサルIDを提供します。 サーバー側転送が動作するためには、事前に ID サービスを実装する必要があります。

## コードバージョン

サーバー側転送には、以下に示すコードライブラリのバージョン 1.5（またはそれ以降）が必要です。ベストプラクティスとして、必要な最小バージョンではなく最新のバージョンを使用することをお勧めします。

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### コードライブラリバージョンの確認

AppMeasurement および訪問者 API コードのバージョン番号は、ブラウザーによって発行された HTTP リクエストを監視するすべてのツールで表示できます。The `AppMeasurement_Module_AudienceManagement.js` does not contain or return a version ID. `AppMeasurement.js` および `VisitorAPI.js` コードのバージョン ID の例を以下に示します。

* `AppMeasurement.js`:次のよ [うなAppMeasurement](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) バージョンが返されます。 `Version of Code | JS-1.5.1`. 他のツールでは異なるラベルが使用される場合がありますが、その値は常に `JS-X.X.X` というパターンに従います。ここで、`X` はバージョン番号です。
* `VisitorAPI.js`:パラメーターを探 `d_visid_ver` します。 It will show you the Visitor ID service like this: `d_visid_ver: 1.5.5`. バージョン 1.5.2 より前の訪問者 API コードにはバージョン番号が含まれていません。監視の結果としてバージョン番号が返されない場合は、古いコードライブラリを使用している可能性があります（アップグレードする必要があります）。
