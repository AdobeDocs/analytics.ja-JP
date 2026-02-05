---
description: 視覚的なオーバーレイを使用してリンクアクティビティをランク付けし、web ページのオーディエンスのエンゲージメントを監視します。
title: Activity Map の概要
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: a7670fcda3e8e6af0c036c8b263746e142278255
workflow-type: ht
source-wordcount: '623'
ht-degree: 100%

---

# Activity Map の概要

Adobe Analytics Activity Map は、Adobe Analytics 内の機能で、web ページやモバイルアプリに対するユーザーエンゲージメントを視覚的に表現します。これにより、マーケターやアナリストは、クリック、スクロール動作などのユーザーインタラクションを追跡および分析できます。Activity Map は、web ページ上で一番人気のある要素を示すヒートマップとオーバーレイレポートを生成し、デジタルエクスペリエンスの最適化に役立ちます。

Activity Map の概念は、次のいくつかの重要なコンポーネントで構成されています。

* **レポートスイート設定**：レポートスイートを使用する前に、Activity Map を有効にする必要があります。レポートスイート設定の [Activity Map レポート](/help/admin/tools/manage-rs/edit-settings/activity-map.md)を参照してください。
* **実装**：ほとんどの Activity Map レポートは標準で使用できます。ただし、一部の web サイトでは、リンクトラッキングを最大限に活用するために追加の実装が必要になる可能性があります。次の実装変数があります。
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md)：リンク名でクリックデータをフィルタリングします。
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md)：地域名でクリックデータをフィルタリングします。
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md)：「Activity Map 地域」ディメンションに入力する属性を変更します。
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md)：Activity Map が「Activity Map リンク」ディメンションの入力に使用するロジックをカスタマイズします。
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md)：Activity Map が「Activity Map 地域」ディメンションの入力に使用するロジックをカスタマイズします。
* **オーバーレイ**：web サイト上にオーバーレイされたクリックデータを表示できるブラウザー拡張機能。詳しくは、[Activity Map 拡張機能インターフェイス](overlay/overview.md)を参照してください。この機能は、Web SDK 実装では使用できません。
* **ディメンション**：オーバーレイ拡張機能に加えて、Activity Map には Analysis Workspace で使用できるいくつかのディメンションが用意されています。
   * [Activity Map リンク](/help/components/dimensions/activity-map-link.md)：クリックしたリンク名。
   * [Activity Map 地域](/help/components/dimensions/activity-map-region.md)：クリックした地域名。
   * [Activity Map ページ](/help/components/dimensions/activity-map-page.md)：リンクをクリックした時点でのページ名。
   * [Activity Map 地域別リンク](/help/components/dimensions/activity-map-link-by-region.md)：Activity Map リンクとActivity Map 地域の連結した値。

## 機能とメリット

* **ユーザーエンゲージメントのビジュアライゼーション**：Activity Map は、ユーザー行動の動的な視覚表示を行うので、ユーザーがクリックした場所を正確に確認できます。この視覚的なデータにより、パターン、トレンド、興味のある領域の特定が簡単になります。その後、デザイン、コンテンツの配置、ユーザーフローについて情報に基づいた決定を行うことができます。

* **ヒートマップ**：Activity Map は、web ページで最もクリックまたはやり取りが多かった領域を表示するヒートマップを生成します。ヒートマップでは、カラーコーディングを使用してエンゲージメントレベルを表すので、ホットスポットを特定し、影響の大きい領域に優先的に注意を向けることができます。この情報は、コールトゥアクションボタン、リンク、フォーム、その他のインタラクティブ要素の最適化に役立ちます。

* **オーバーレイレポート**：Activity Map のオーバーレイレポートは、web ページ上の特定の要素に関する詳細なクリック指標を提供します。個々の要素のクリックスルー率とエンゲージメントレベルを理解することで、デザインとコンテンツ戦略を微調整して、ユーザーエクスペリエンスを強化できます。この機能は、Web SDK 実装では使用できません。

* **セグメント分析**：トラフィックソース、人口統計、ペルソナなどの様々なセグメントに基づいてユーザー行動を分析できます。 データをセグメント化することで、特定のユーザーグループに関する貴重なインサイトを明らかにし、パーソナライズされたエクスペリエンスとターゲットを絞ったマーケティング戦略を実現できます。

## 実用的な用途

* **Web サイトの最適化**：Activity Map は、パフォーマンスの低い要素を特定し、ナビゲーションを改善し、全体的なユーザーエクスペリエンスを向上させることで、web サイトを最適化するのに役立ちます。ユーザーインタラクションを分析することで、データ主導型の決定を行って、ユーザーフローを効率化し、フォームを簡素化し、最大の効果を得るためにコンテンツの配置を調整できます。

* **コンバージョン率の最適化**：ユーザーエンゲージメントを視覚化し、クリックスルー率を分析することにより、Activity Map は CRO の取り組みに重要な役割を果たします。コンバージョンに対する障壁を特定し、様々なデザインのバリエーションを実験して、コンバージョンファネル、ランディングページ、チェックアウトプロセスを最適化できます。

* **A/B テスト**：Activity Map を A/B テストと組み合わせて、デザインやコンテンツの変更の影響を測定できます。様々なバージョンの web ページのエンゲージメント指標を比較することで、より高いユーザーエンゲージメント、コンバージョン率、売上高につながるバリエーションを判断できます。

