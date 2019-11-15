---
description: appFiguresの統合は、多くの場合、複数のアプリストアにまたがる複数のアプリ用のデータを収集するために使用されます。 セグメントを作成して、特定のアプリまたはアプリストアのレポートデータを分離できます。
title: アプリデータのセグメント化
uuid: 9c2aaf0d-088f-4178-8ed1-a8124087a683
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# アプリデータのセグメント化{#segmenting-app-data}

appFiguresの統合は、多くの場合、複数のアプリストアにまたがる複数のアプリ用のデータを収集するために使用されます。 セグメントを作成して、特定のアプリまたはアプリストアのレポートデータを分離できます。

appFiguresデータのセグメント化のガイドライン：

* ページビューコンテナのみを使用する必要があります。
* フィルタリングルールで [はAppFiguresディメンションのみ](/help/import/data-connectors/appfigures-overview/appfigures-metrics.md) を使用する必要があります。
* AppFiguresディメンションのみが参照されている限り、複数のセグメントル [ールを使用でき](/help/import/data-connectors/appfigures-overview/appfigures-segment-filter.md) ます。
* [以下を含む]キャンバスと[以下を除外する]キャンバスの両方を使用できます。
* セグメントはAdobe Analytics v15にのみ適用されます。
