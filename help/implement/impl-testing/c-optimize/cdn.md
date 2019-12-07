---
description: Akamai、Speedera などのコンテンツ配信サービスまたはコンテンツ配信ネットワーク（CDN）は、Web コンテンツをネットワークの末端近くにまでプッシュして、頻繁に要求されるドキュメントをアクセスされる場所の近くで保持します。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: コンテンツ配信サービスおよびコンテンツ配信ネットワーク
topic: Developer and implementation
uuid: 6cb57c59-d0f9-4ca5-9f15-0e74e585a4a1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# コンテンツ配信サービスおよびコンテンツ配信ネットワーク

Akamai、Speedera などのコンテンツ配信サービスまたはコンテンツ配信ネットワーク（CDN）は、Web コンテンツをネットワークの末端近くにまでプッシュして、頻繁に要求されるドキュメントをアクセスされる場所の近くで保持します。

これにより通常はアクセスの待ち時間が短縮し、帯域幅の使用量が減少し、インフラストラクチャのコストも削減されます。

JavaScript 版 AppMeasurement ライブラリファイルを CDN 経由で配信して、サイト訪問者に対するパフォーマンスおよびファイル配信を強化できます。アドビのお客様は、CDN サービスを正しく構成したことを確認する必要があります。CDN はダウンロード時間の変動の主な原因となるので、ダウンロード時間に何らかの変動があった場合に最も可能性の高い原因として考える必要があります。

タグマネージャーによって、すべての JavaScript が CDN に保存されます。
