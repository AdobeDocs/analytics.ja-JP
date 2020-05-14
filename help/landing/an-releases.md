---
description: Adobe Analyticsの新しい継続的な機能のリリース方法を説明します。
title: Adobe Analytics — 機能リリース戦略
translation-type: tm+mt
source-git-commit: 0b00405e9e27a427a85b0f4a0d970671ada4aa67
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# Adobe Analytics — 機能リリース戦略

これまで、Adobe Analyticsの機能リリースは、固定の月次スケジュールに従っていました。 2020年4月より、Adobe Analyticsは、機能の導入に向けて、よりスケーラブルで段階的なアプローチを可能にする、継続的な配信モデルに移行します。

## リリース方法

[!UICONTROL 分析ワークスペース] では、機能フラグ（「トグル」とも呼ばれます）を使用して新機能の表示/非表示を制御し、完全リリース前の制御スケールテストを行うことができます。 このリリース戦略には、次のフェーズが含まれます。

* **実稼働環境(RTP)にリリース**: コードが実稼動環境にリリースされ、分析ワークスペースでの機能の表示がオフになっています。 **注意**: 現時点では、この機能は2.0 Analytics APIで使用できます。

* **制限付きテスト**: 段階的なリリースは、アドビの内部ユーザーによるテストで始まります。 このリリースでは、数か月の間に0%から100%の可用性に拡張されます。 Experience Cloud組織レベルで展開が段階的に行われるので、組織内の権利付与済みユーザーはすべて同じエクスペリエンスを受け取ります。

* **GA (General Availability)**: この機能は、権利が付与されているExperience Cloud組織の100%が利用でき、機能のリリースが完了しました。

各機能リリースにより、RTPからGAまでのタイムラインが変わる場合があります。 目標は、リリース開始(RTP)から2か月以内に機能がGAになるように、リリースを短く保つことです。

## メリット

各段階的なリリースにより、アドビはソフトウェアの展開プロセスをより適切に拡張でき、一般公開の前に機能を完全に強化できます。 また、毎月の固定リリースウィンドウを守らずに、機能が使用可能になったらすぐにリリースできます。

## よくある質問（FAQ）

| 質問 | 回答 |
|---|---|
| 機能への早期アクセスをリクエストできますか？ | いいえ。早期アクセスは許可されません。<br>初期のAnalyticsの概念をテストする場合は、 [Adobe Analytics Labs](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/tech-previews/overview.html) （英語のみ）で業界をリードする革新的な技術革新に関するフィードバックをお送りすることをお勧めします。 |
| このリリース戦略は、機能へのアクセスに影響を与えますか。 | いいえ。機能がGAに達すると、その機能がAnalyticsパッケージに含まれている場合は、その機能にアクセスできます。<br>Analyticsパッケージの表示の詳細は、 [!UICONTROL 管理者] / [!UICONTROL 会社設定] / [機能アクセスレベルで確認できます](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html)。 |