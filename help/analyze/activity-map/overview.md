---
description: 視覚的なオーバーレイを使用してリンクアクティビティをランク付けし、web ページのオーディエンスのエンゲージメントを監視します。
title: Activity Map の概要
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 4%

---

# Activity Map の概要

Adobe Analytics Activity Map は、Adobe Analytics 内の機能で、web ページやモバイルアプリに対するユーザーエンゲージメントを視覚的に表現します。マーケターやアナリストは、クリックやスクロール動作などのユーザーインタラクションを追跡および分析できます。 Activity Mapは、Web ページ上で最も人気のある要素を示すヒートマップとオーバーレイレポートを生成し、デジタルエクスペリエンスの最適化に役立ちます。

この節のドキュメントでは、Activity Mapオーバーレイに焦点を当てています。 ただし、Activity Mapを使用する際に重要なポイントは他にもあります。

* **レポートスイートの設定**：レポートスイートでActivity Mapが有効になっている必要があります。 レポートスイートの設定で ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)0}Activity Mapレポート } を参照してください。[
* **実装**：ほとんどのActivity Mapレポートは、すぐに使用できます。 ただし、リンクトラッキングを最大限に活用するために、追加の実装が必要な web サイトもあります。 次の実装変数を使用できます。
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md)：クリックデータをリンク名でフィルタリングします。
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md)：地域名でクリックデータをフィルタリングします。
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): 「Activity Mapリージョン」ディメンションを移入する属性を変更します。
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md):Activity Mapリンクディメンションの入力にActivity Mapが使用するロジックをカスタマイズします。
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md):Activity Map地域ディメンションの入力にActivity Mapが使用するロジックをカスタマイズします。
* **Dimension**: オーバーレイ拡張機能に加えて、Activity MapにはAnalysis Workspaceで使用できる寸法がいくつか用意されています。
   * [Activity Mapリンク ](/help/components/dimensions/activity-map-link.md): クリックされたリンク名。
   * [Activity Map地域 ](/help/components/dimensions/activity-map-region.md): クリックされた地域名。
   * [Activity Mapページ ](/help/components/dimensions/activity-map-page.md): リンクがクリックされた時点でのページ名。
   * [Activity Mapリンク （リージョン別） ](/help/components/dimensions/activity-map-link-by-region.md):Activity MapリンクとActivity Mapリージョンを連結した値。

## 機能とメリット

* **ユーザーエンゲージメントのビジュアライゼーション**:Activity Mapは、ユーザーの行動を動的かつ視覚的に表示し、ユーザーのクリックした場所を正確に確認できます。 このような視覚的なデータにより、パターン、トレンドおよび関心のある領域を簡単に特定できます。 その後、デザイン、コンテンツ配置、ユーザーフローについて十分な情報に基づいた決定を下すことができます。

* **ヒートマップ**:Activity Mapは、Web ページの最もクリックされた領域やインタラクションのある領域を表示するヒートマップを生成します。 ヒートマップでは、色分けを使用してエンゲージメントレベルを表すことで、ホットスポットを特定し、影響の大きい領域への注目を優先させることができます。 この情報は、コールトゥアクションボタン、リンク、フォームまたはその他のインタラクティブ要素を最適化する際に役立ちます。

* **レポートをオーバーレイ**:Activity Mapのオーバーレイレポートは、web ページ上の特定の要素に対する詳細なクリック指標を提供します。 個々の要素のクリックスルー率とエンゲージメントレベルを把握することで、デザインとコンテンツ戦略を微調整して、ユーザーエクスペリエンスを強化できます。

* **セグメント分析**：トラフィックソース、人口統計、ペルソナなど、様々なセグメントに基づいて、ユーザーの行動を分析できます。 データをセグメント化することで、貴重なインサイトを特定のユーザーグループに明らかにし、パーソナライズされたエクスペリエンスやターゲットを絞ったマーケティング戦略を可能にすることができます。

## 実用化

* **Web サイトの最適化**:Activity Mapを使用すると、パフォーマンスの低い要素を特定し、ナビゲーションを向上させ、全体的なユーザーエクスペリエンスを強化することで、web サイトを最適化できます。 ユーザーインタラクションを分析することで、データに基づく意思決定を行い、ユーザーフローを合理化し、フォームを簡素化し、最大限の影響を得るためにコンテンツの配置を調整できます。

* **コンバージョン率の最適化**：ユーザーエンゲージメントを視覚化し、クリックスルー率を分析することで、Activity Mapは CRO の取り組みにおいて重要な役割を果たします。 コンバージョンの障壁を特定し、様々なデザインバリエーションを試して、コンバージョンファネル、ランディングページおよびチェックアウトプロセスを最適化できます。

* **A/B テスト**:Activity Mapと A/B テストを組み合わせて、デザインまたはコンテンツの変更の影響を測定できます。 Web ページの異なるバージョン間でエンゲージメント指標を比較することで、どのバリエーションがより高いユーザーエンゲージメント、コンバージョン率または売上高につながるかを判断できます。

* **モバイルアプリの最適化**:Activity Mapは web サイトに限定されません。モバイルアプリケーションにも機能を拡張します。 アプリ内のユーザーのインタラクションに関するインサイトを得ることができ、操作性の向上、ナビゲーションの強化、シームレスなモバイルエクスペリエンスを実現するための機能の調整を行うことができます。
