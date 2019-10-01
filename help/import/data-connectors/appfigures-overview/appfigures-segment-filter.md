---
description: appFiguresの統合は、多くの場合、複数のアプリストアにまたがる複数のアプリ用のデータを収集するために使用されます。 セグメントを作成して、特定のアプリまたはアプリストアのレポートデータを分離できます。
seo-description: appFiguresの統合は、多くの場合、複数のアプリストアにまたがる複数のアプリ用のデータを収集するために使用されます。 セグメントを作成して、特定のアプリまたはアプリストアのレポートデータを分離できます。
seo-title: アプリデータのセグメント化
title: アプリデータのセグメント化
uuid: 9c2aaf0d-088f-4178-8ed1-a8124087a683
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# アプリデータのセグメント化{#segmenting-app-data}

appFiguresの統合は、多くの場合、複数のアプリストアにまたがる複数のアプリ用のデータを収集するために使用されます。 セグメントを作成して、特定のアプリまたはアプリストアのレポートデータを分離できます。

appFiguresデータのセグメント化のガイドライン：

* ページビューコンテナのみを使用する必要があります。
* フィルタリングルールで [はAppFiguresディメンションのみ](../appfigures-overview/appfigures-metrics.md#concept-890b06e6f59e44a7a331ce872f4e1d9c) を使用する必要があります。
* AppFiguresディメンションのみが参照されている限り、複数のセグメントル [ールを使用でき](../appfigures-overview/appfigures-metrics.md#concept-890b06e6f59e44a7a331ce872f4e1d9c) ます。
* [以下を含む]キャンバスと[以下を除外する]キャンバスの両方を使用できます。
* セグメントはAdobe Analytics v15にのみ適用されます。
