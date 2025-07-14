---
description: 視覚的なオーバーレイを使用してリンクアクティビティをランク付けし、web ページのオーディエンスのエンゲージメントを監視します。
title: Activity Map の概要
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: dee8f0a13a159f4c7902d2ccddd8848c4016b471
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 5%

---

# Activity Map の概要

Adobe Analytics Activity Map は、Adobe Analytics 内の機能で、web ページやモバイルアプリに対するユーザーエンゲージメントを視覚的に表現します。マーケターやアナリストは、クリックやスクロール動作などのユーザーインタラクションを追跡および分析できます。 Activity Mapは、Web ページ上で最も人気のある要素を示すヒートマップとオーバーレイレポートを生成し、デジタルエクスペリエンスの最適化に役立ちます。

この節のドキュメントでは、Activity Mapのオーバーレイに焦点を当てています。 ただし、Activity Mapを使用する際に重要なその他の点は次のとおりです。

* **レポートスイートの設定**：レポートスイートでは、Activity Mapが有効になっている必要があります。 レポートスイートの設定で [0&rbrace;Activity Map レポート &rbrace; を参照してください。](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
* **実装**：ほとんどのActivity Map レポートは、すぐに使用できます。 ただし、リンクトラッキングを最大限に活用するために、追加の実装が必要な web サイトもあります。 次の実装変数を使用できます。
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md)：クリックデータをリンク名でフィルタリングします。
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md)：地域名でクリックデータをフィルタリングします。
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): 「Activity Map リージョン」ディメンションを移入する属性を変更します。
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md):Activity Map リンクディメンションの入力にActivity Mapが使用するロジックをカスタマイズします。
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md):Activity Map地域ディメンションの入力にActivity Mapが使用するロジックをカスタマイズします。
* **寸法**：オーバーレイ拡張機能に加えて、Activity MapにはAnalysis Workspaceで使用できる寸法がいくつか用意されています。
   * [Activity Map リンク ](/help/components/dimensions/activity-map-link.md): クリックされたリンク名。
   * [Activity Map地域 ](/help/components/dimensions/activity-map-region.md): クリックされた地域名。
   * [Activity Mapページ ](/help/components/dimensions/activity-map-page.md): リンクがクリックされた時点でのページ名。
   * [Activity Map リンク （リージョン別） ](/help/components/dimensions/activity-map-link-by-region.md): Activity Map リンクとActivity Map リージョンを連結した値。

## 機能とメリット

* **ユーザーエンゲージメントのビジュアライゼーション**:Activity Mapは、ユーザーの行動を動的かつ視覚的に表示し、ユーザーのクリックした場所を正確に確認できます。 このような視覚的なデータにより、パターン、トレンドおよび関心のある領域を簡単に特定できます。 その後、デザイン、コンテンツ配置、ユーザーフローについて十分な情報に基づいた決定を下すことができます。

* **ヒートマップ**:Activity Mapは、Web ページの最もクリックされた領域やインタラクションのある領域を表示するヒートマップを生成します。 ヒートマップでは、色分けを使用してエンゲージメントレベルを表すことで、ホットスポットを特定し、影響の大きい領域への注目を優先させることができます。 この情報は、call-to-actionのボタン、リンク、フォームまたはその他のインタラクティブな要素を最適化する際に役立ちます。

* **オーバーレイレポート**:Activity Mapのオーバーレイレポートは、web ページ上の特定の要素に対する詳細なクリック指標を提供します。 個々の要素のクリックスルー率とエンゲージメントレベルを把握することで、デザインとコンテンツ戦略を微調整して、ユーザーエクスペリエンスを強化できます。

* **セグメント分析**：トラフィックソース、人口統計、ペルソナなど、様々なセグメントに基づいて、ユーザーの行動を分析できます。 データをセグメント化することで、貴重なインサイトを特定のユーザーグループに明らかにし、パーソナライズされたエクスペリエンスやターゲットを絞ったマーケティング戦略を可能にすることができます。

## 実用化

* **Web サイトの最適化**:Activity Mapを使用すると、パフォーマンスの低い要素を特定し、ナビゲーションを強化し、全体的なユーザーエクスペリエンスを強化することで、web サイトを最適化できます。 ユーザーインタラクションを分析することで、データに基づく意思決定を行い、ユーザーフローを合理化し、フォームを簡素化し、最大限の影響を得るためにコンテンツの配置を調整できます。

* **コンバージョン率の最適化**：ユーザーエンゲージメントを視覚化し、クリックスルー率を分析することで、Activity Mapは CRO の取り組みにおいて重要な役割を果たします。 コンバージョンの障壁を特定し、様々なデザインバリエーションを試して、コンバージョンファネル、ランディングページおよびチェックアウトプロセスを最適化できます。

* **A/B テスト**: Activity Mapを A/B テストと組み合わせて、デザインまたはコンテンツの変更の影響を測定できます。 Web ページの異なるバージョン間でエンゲージメント指標を比較することで、どのバリエーションがより高いユーザーエンゲージメント、コンバージョン率または売上高につながるかを判断できます。

