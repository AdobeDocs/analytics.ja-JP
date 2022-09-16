---
description: サーバー側転送を実装するには、次の Experience Cloud ソリューション、サービス、コードの要件を満たす必要があります。この要件の説明には、コードのバージョンを確認するための手順と最新のコードライブラリの入手先も含まれています。
solution: Analytics
title: サーバー側転送の要件
feature: Server-Side Forwarding
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 100%

---

# サーバー側転送の要件

サーバー側転送を実装するには、次の Experience Cloud ソリューション、サービス、コードの要件を満たす必要があります。この要件の説明には、コードのバージョンを確認するための手順と最新のコードライブラリの入手先も含まれています。

## ソリューションの要件

サーバー側転送は、[Analytics](https://www.adobe.com/jp/data-analytics-cloud/analytics.html)、[Audience Manager](https://www.adobe.com/jp/analytics/audience-manager.html) および [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=ja) に対応しています。

## サービスの要件

サーバー側転送には、[ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)が必要です。ID サービスは、Experience Cloud のすべてのソリューションにわたってサイトの訪問者を識別する、普遍的な ID を提供します。サーバー側転送が動作するためには、事前に ID サービスを実装する必要があります。

## コードバージョン

サーバー側転送には、以下に示すコードライブラリのバージョン 1.5（またはそれ以降）が必要です。ベストプラクティスとして、必要な最小バージョンではなく最新のバージョンを使用することをお勧めします。

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### コードライブラリバージョンの確認

AppMeasurement および訪問者 API コードのバージョン番号は、ブラウザーによって発行された HTTP リクエストを監視するすべてのツールで表示できます。`AppMeasurement_Module_AudienceManagement.js` の場合は、バージョン ID が含まれず、この値は返されません。`AppMeasurement.js` および `VisitorAPI.js` コードのバージョン ID の例を以下に示します。

* `AppMeasurement.js`：[Adobe Debugger](https://experienceleague.adobe.com/docs/analytics/implementation/validate/debugger.html?lang=ja) は、`Version of Code | JS-1.5.1` という形式で AppMeasurement バージョンを返します。他のツールでは異なるラベルが使用される場合がありますが、その値は常に `JS-X.X.X` というパターンに従います。ここで、`X` はバージョン番号です。
* `VisitorAPI.js`：`d_visid_ver` パラメーターを探します。訪問者 ID サービスが `d_visid_ver: 1.5.5` という形式で表示されます。バージョン 1.5.2 より前の訪問者 API コードにはバージョン番号が含まれていません。監視の結果としてバージョン番号が返されない場合は、古いコードライブラリを使用している可能性があります（アップグレードする必要があります）。
