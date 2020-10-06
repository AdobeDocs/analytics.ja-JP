---
description: Adobe Analytics の新しい継続的な機能リリース戦略を説明します。
title: Adobe Analytics 機能リリース
translation-type: ht
source-git-commit: bbbe6dccfee81ae5111f295906aa3a23d68ad39e
workflow-type: ht
source-wordcount: '422'
ht-degree: 100%

---


# Adobe Analytics 機能リリース

これまで、Adobe Analytics の機能リリースは、毎月の固定スケジュールに従っていました。2020 年 4 月より、Adobe Analytics は、機能のデプロイメントに向けて、よりスケーラブルで段階的なアプローチを可能にする、継続的な配信モデルに移行しました。

## リリース方法

[!UICONTROL Analysis Workspace] では、機能フラグ（「トグル」とも呼ばれます）を使用して新機能の表示/非表示を制御し、完全リリース前の制御スケールテストをおこなうことができます。このリリース戦略には、次のフェーズが含まれます。

* **実稼働環境（RTP）にリリース**: コードが実稼動環境にリリースされ、Analysis Workspace での機能の表示がオフになっています。**注意**：RTP では、この機能は 2.0 Analytics API で使用できます。

* **制限付きテスト**：段階的なリリースは、アドビの内部ユーザーによるテストで始まります。このリリースでは、数か月の間に 0% から 100% の可用性に拡張されます。Experience Cloud 組織レベルで展開が段階的に行われるので、組織内の権利を持つすべてのユーザーは同じエクスペリエンスを受け取ります。

* **GA (General Availability)**：この機能は、権利を付与されている Experience Cloud の組織の 100% が利用でき、機能のリリースが完了しました。

各機能リリースにより、RTP から GA までのタイムラインが変わる場合があります。目標は、リリース開始（RTP）から 2 か月以内に機能が GA になるように、リリースを短く保つことです。

## 機能フラグ

機能フラグは、リリース時の新機能の表示を制御するために使用します。リリース時に最適なエクスペリエンスを得るために、app.launchdarkly.com をファイアウォールの [許可リスト](https://docs.adobe.com/content/help/ja-JP/analytics/technotes/ip-addresses.html)に追加することを推奨します。GA に達した直後に、フラグが削除されます。

アクティブな機能フラグは、**ヘルプ／Workspace について／アクティブな機能フラグ**&#x200B;からいつでも表示できます。

## メリット

各段階的なリリースにより、アドビはソフトウェアのデプロイメントプロセスをより適切に拡張でき、一般公開の前に機能を完全に強化できます。また、毎月の固定リリースウィンドウを守らずに、機能が使用可能になったらすぐにリリースできます。

## よくある質問（FAQ）

| 質問 | 回答 |
|---|---|
| 機能への早期アクセスをリクエストできますか？ | いいえ。早期アクセスは許可されません。<br>Analytics の初期の概念をテストする場合は、[Adobe Analytics Labs](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/tech-previews/overview.html) で業界をリードする革新的なアイデアに対するフィードバックを提供してみることをお勧めします 。 |
| このリリース戦略は、機能へのアクセスに影響を与えますか。 | いいえ。機能が GA に達すると、その機能が Analytics パッケージに含まれている場合はアクセスできます。<br>Analytics パッケージの表示の詳細は、[!UICONTROL 管理者]／[!UICONTROL 会社設定]／[機能アクセスレベル](https://docs.adobe.com/content/help/ja-JP/analytics/admin/company-settings/feature-access-levels.html)で確認できます。 |
