---
description: データプライバシーの同意管理用の変数。
seo-description: データプライバシーの同意管理用の変数。
seo-title: 同意管理変数
solution: Analytics
title: 同意管理変数
topic: 管理ツール
translation-type: tm+mt
source-git-commit: 492e9405c82183f6beb6588cd0dc039fe15350f7

---


# 同意管理変数

プライバシーデータの管理に関する追加の支援を提供するために、一連の予約済み変数を特定のコンテキストデータ変数と組み合わせて使用できます。
これらの同意管理変数は、各分析ヒットの同意ステータスを捕捉するための使いやすいフレームワークを提供します。

## 変数

* 同意管理のオプトアウト
   * 予約変数：リストprop
   * タイプ：コンマ区切り文字列
   * 次を含む:
      * `contextData.['cm.ssf']=1` SSFとして表示
      * `contextData.['opt.dmp']=N` DMPとして表示
      * `contextData.['opt.sell']=N` SELLとして表示

* 同意管理のオプトイン
   * 予約変数：リストprop
   * タイプ：コンマ区切り文字列
   * 次を含む:
      * `contextData.['opt.dmp']=Y` DMPとして表示
      * `contextData.['opt.sell']=Y` SELLとして表示

## レポート

同意管理変数は、Analytics管理コンソール内の新しいプライバシー設定を使用して有効にできます。

各レポートスイートは、次のように設定できます。
1. Reports &amp; Analyticsで、管理者/レポートスイートの順にクリックします。
1. Select the report suite(s) where you are collecting media data and click [!UICONTROL Edit Settings &gt; Privacy Management]

   ![](assets/rsm-privacy-select.png)

1. 「データプライバシー [!UICONTROL レポートを有効にする] 」ボタンをクリックします。  注：有効化した後で、これらの変数をオフにすることはできません。

   ![](assets/rsm-privacy-enable.png)

1. 有効にすると、確認メッセージが表示されます。

   ![](assets/rsm-privacy-config.png)

1. 予約変数がレポートで使用できるようになりました。  「同意管理オプトアウト」および「同意管理オプトイン」を参照してください。

   ![](assets/rsm-privacy-reports.png)

## 実装

同意管理予約変数を使用するために、3つのコンテキストデータ変数が事前に定義されています。  これらの変数の管理方法と設定の永続化方法は、各導入エンジニアが決定します。

コンテキスト [データ変数の実装に関する一般的なガイダンスは](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) 、「コンテキストデータ変数」を参照してください。

### SSF

* コンテキストデータ：`contextData.['cm.ssf']`
* 指定可能な値：
   * `1`  — 値を送信するときに、サ `1`ーバー側転送がオプトアウト状態にあることを示します。 この変数と `1` 対になる値は、Adobe Audience Managerとのこのヒットの共有をブロックします。 AAM ePrivacy Complianceを参 [照してください。](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * このパラメーターには他の値は使用できません

### DMP

* コンテキストデータ：`contextData.['opt.dmp']`
* 指定可能な値：
   * `N`  — 値を送信するとき、こ `N`れは、コンシューマーがデータ管理プラットフォームへの共有をオプトアウトしていることを示します。 AAMへの現在のブロック共有は行われません。  その機能にはSSFを使用します。
   * `Y`  — 値を送信する際に、コンシューマ `Y`ーがデータ管理プラットフォームへの共有をオプトインしていることを示します。

### 販売

* コンテキストデータ：`contextData.['opt.sell']`
* 指定可能な値：
   * `N` ・価値を送信する際に、 `N`消費者がデータの共有や販売を第三者にオプトアウトしていることを示す。
   * `Y` ・価値を送信する際に、 `Y`消費者がデータの共有や第三者への販売を選択していることを示す。
