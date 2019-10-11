---
description: データプライバシーの同意管理用の変数。
seo-description: データプライバシーの同意管理用の変数。
seo-title: 同意管理変数
solution: Analytics
title: 同意管理変数
topic: 管理ツール
translation-type: tm+mt
source-git-commit: 69f7ab75d95373754c0f4285c9d688d1c7d12322

---


# 同意管理変数

プライバシーデータの管理に関する追加の支援を提供するために、一連の予約済み変数を特定のコンテキストデータ変数と組み合わせて使用できます。
これらの同意管理変数は、各分析ヒットの同意ステータスを取得するための使いやすいフレームワークです。

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

Analytics管理コンソール内で利用可能な新しいプライバシー設定を使用して、同意管理変数を有効にできます。

各レポートスイートは、次のように設定できます。
1. In Reports &amp; Analytics click **[!UICONTROL Admin &gt; Report Suites.]**
1. Select the report suite(s) where you are collecting media data and click **[!UICONTROL Edit Settings &gt; Privacy Management.]**

   ![](assets/rsm-privacy-select.png)

1. 「データプライバシー **[!UICONTROL レポートを有効にする]** 」ボタンをクリックします。 **** 注意：一旦有効にすると、これらの変数はオフにできません。

   ![](assets/rsm-privacy-enable.png)

1. 有効にすると、確認メッセージが表示されます。

   ![](assets/rsm-privacy-config.png)

1. 予約変数がレポートで使用できるようになりました。  「同意管理オプトアウト」および「同意管理オプトイン」を参照してください。

   ![](assets/rsm-privacy-reports.png)

## 実装

同意管理予約変数を使用するために、3つのコンテキストデータ変数が事前に定義されています。  これらの変数の管理方法と設定の永続化方法は、各導入エンジニアが決定します。

コンテキスト [データ変数の実装に関する一般的なガイダンスは](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) 、「コンテキストデータ変数」を参照してください。

### SSF

* コンテキストデータ：contextData。['cm.ssf']
* 指定可能な値：
   * 1 — 値「1」を送信する場合、これはサーバー側転送がオプトアウト状態であることを示します。 この変数と対になる値「1」は、Adobe Audience Managerとのこのヒットの共有をブロックします。 AAM ePrivacy Complianceを参 [照してください。](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * このパラメーターには、他の値は使用できません。

### DMP

* コンテキストデータ：contextData。['opt.dmp']
* 指定可能な値：
   * N — 値「N」を送信する場合、コンシューマーがデータ管理プラットフォームへの共有をオプトアウトしていることを示します。 **** 注意：この変数を「N」に設定しても、現在AAMへの共有はブロックされませんが、AAM機能の呼び出しをブロックする機能は、2020年の初めに追加される予定です。 現在のところ、AAMにヒットが送信され `c.cm.ssf=1` るのをブ `c.opt.dmp=N` ロックするように、との両方を設定することをお勧めします。
   * Y — 値「Y」を送信すると、コンシューマーがデータ管理プラットフォームへの共有を選択していることを示します。

### 販売

* コンテキストデータ：contextData。['opt.sell']
* 指定可能な値：
   * N — 値「N」を送信する場合、消費者がデータの共有または販売を第三者にオプトアウトしていることを示します。
   * Y — 値「Y」を送信する場合、消費者がデータの共有または第三者への販売を選択していることを示します。
