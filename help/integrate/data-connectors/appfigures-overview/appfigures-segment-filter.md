---
description: appFigures統合は、複数のアプリケーションストアにまたがる複数のアプリケーション用にデータを収集するためによく使用されます。セグメントを作成して、特定のアプリまたはアプリストアのレポートデータを分離できます。
seo-description: appFigures統合は、複数のアプリケーションストアにまたがる複数のアプリケーション用にデータを収集するためによく使用されます。セグメントを作成して、特定のアプリまたはアプリストアのレポートデータを分離できます。
seo-title: アプリケーションデータのセグメント化
title: アプリケーションデータのセグメント化
uuid: 9c2aaf0d-088f-4178-8ed1- a8124087a683
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Segmenting App Data{#segmenting-app-data}

appFigures統合は、複数のアプリケーションストアにまたがる複数のアプリケーション用にデータを収集するためによく使用されます。セグメントを作成して、特定のアプリまたはアプリストアのレポートデータを分離できます。

appFiguresデータのセグメント化ガイドライン:

* ページビューコンテナのみを使用する必要があります。
* Must use only [AppFigures dimensions](../appfigures-overview/appfigures-metrics.md#concept-890b06e6f59e44a7a331ce872f4e1d9c) in filtering rules.
* [appFiguresのディメンション](../appfigures-overview/appfigures-metrics.md#concept-890b06e6f59e44a7a331ce872f4e1d9c) のみが参照されている場合は、複数のセグメントルールを使用できます。
* [以下を含む]キャンバスと[以下を除外する]キャンバスの両方を使用できます。
* セグメントはAdobe Analytics v15にのみ適用されます。

