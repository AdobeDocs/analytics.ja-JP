---
description: データプライバシーにおけるプライバシーレポート用変数。
title: プライバシーレポート変数
topic: Admin tools
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# プライバシーレポート変数

プライバシーデータ管理に関する追加の支援を提供するために、一連の予約済み変数を特定のコンテキストデータ変数と組み合わせて使用できます。
これらのプライバシーレポート変数は、各分析ヒットのプライバシーステータスを取り込むための使いやすいフレームワークです。

## 変数

* 同意管理のオプトアウト
   * 予約変数：リスト prop
   * タイプ：コンマ区切り文字列
   * 次を含む：
      * SSF として表示される `contextData.['cm.ssf']=1`
      * DMP として表示される `contextData.['opt.dmp']=N`
      * SELL として表示される `contextData.['opt.sell']=N`

* 同意管理のオプトイン
   * 予約変数：リスト prop
   * タイプ：コンマ区切り文字列
   * 次を含む：
      * DMP として表示される `contextData.['opt.dmp']=Y`
      * SELL として表示される `contextData.['opt.sell']=Y`

## レポート

Analytics Admin Console で利用できる新しいプライバシー設定を使用して、プライバシーレポート変数を有効にできます。

各レポートスイートは、次のように設定できます。
1. Reports &amp; Analytics で、**[!UICONTROL 管理者／レポートスイート]**&#x200B;をクリックします。
1. メディアデータを収集するレポートスイートを選択して、**[!UICONTROL 設定を編集／プライバシー管理]**&#x200B;をクリックします。

   ![](assets/rsm-privacy-select.png)

1. 「**[!UICONTROL データプライバシー レポートを有効にする]**」ボタンをクリックします。

   > [!NOTE]有効化した後で、これらの変数をオフにすることはできません。

   ![](assets/rsm-privacy-enable.png)

1. 有効にすると、確認メッセージが表示されます。

   ![](assets/rsm-privacy-config.png)

1. 予約変数がレポートで使用できるようになりました。「同意管理のオプトアウト」および「同意管理のオプトイン」を参照してください。

   ![](assets/rsm-privacy-reports.png)

## 実装

3 つのコンテキストデータ変数が、プライバシーレポート管理予約変数と連携するように事前に定義されています。これらの変数の設定の管理方法と保持の方法は、各実装エンジニアが決定します。

コンテキスト データ変数の実装に関する一般的なガイダンスについては、[コンテキストデータ変数](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html)を参照してください。

### SSF

* コンテキストデータ：`contextData.['cm.ssf']`
* 指定可能な値：
   * 1：値「1」を送信する場合は、サーバー側転送がオプトアウト状態であることを示します。この変数と対になる値「1」は、このヒットが Adobe Audience Manager と共有されるのをブロックします。[AAM ePrivacy のコンプライアンス](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)を参照してください。
   * このパラメーターには、他の値は使用できません。

### DMP

* コンテキストデータ：`contextData.['opt.dmp']`
* 指定可能な値：
   * N：値「N」を送信すると、データ管理プラットフォームへの共有をコンシューマーがオプトアウトしていることを示します。**注**：現在、この変数を「N」に設定しても AAM への共有はブロックされませんが、2020 年初めに AAM 機能の呼び出しをブロックする機能が追加される予定です。現時点では、AAM にヒットが送信されるのを防ぐよう、`c.cm.ssf=1` と `c.opt.dmp=N` の両方を設定することをお勧めします。
   * Y：値「Y」を送信すると、データ管理プラットフォームへの共有をコンシューマーがオプトインしていることを示します。

### SELL

* コンテキストデータ：`contextData.['opt.sell']`
* 指定可能な値：
   * N：値「N」を送信すると、データをサードパーティへのデータの共有または販売を、コンシューマーがオプトアウトしていることを示します。
   * Y：値「Y」を送信すると、データをサードパーティへのデータの共有または販売を、コンシューマーがオプトインしていることを示します。
