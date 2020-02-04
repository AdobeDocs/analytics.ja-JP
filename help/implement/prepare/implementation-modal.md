---
title: 実装モーダル
description: Adobe Analytics 実装を初めて実装する場合について説明します。
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 実装モーダル

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

「Adobe Analyticsへようこそ」モーダルウィンドウでは、レポートスイートを作成するためのワークフローがシンプルになります。 組織でさらに多くのレポートスイートが必要な場合は、このワークフローを使用することをお勧めします。

![モーダルスクリーンショット](assets/implementation-modal.png)

## 前提条件

Adobe IDは、Adobe AnalyticsとAdobe Experience Platform Launchの両方にアクセスできる必要があります。 「起動」へのアクセス権がない場合は、認証ループに配置し、資格情報を無期限に検証するように求めることができます。 組織のシステム管理者に問い合わせて、「起動」へのアクセス権を取得します。

## モーダルにアクセス

次の手順を使用して、モーダルにアクセスし、レポートスイートを作成します。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. Click the 9-grid icon at the top, then click [!UICONTROL Adobe Analytics].
3. まだレポートスイートを作成していない場合は、モーダルが自動的に表示されます。 このログイン会社用のレポートスイートが存在する場合は、右上のヘルプアイコンをクリックし、「Adobe Analyticsへよう [!UICONTROL こそ」をクリックします]。

> [!NOTE] 「Adobe Analytics [!UICONTROL へようこそ] 」オプションは、Adobe Experience cloud経由でログインした場合にのみ表示されます。 既存のドメインを使用してログインした場合、モーダルは使用できません。

## レポートスイートの作成

[セットアップの [!UICONTROL 開始] ]ボタンをクリックして、レポートスイート作成ワークフローを開始します。

![RSウィザード](assets/analytics-implementation-rs-wizard.png)

### プロパティタイプ

プロパティタイプは、Analyticsを実装する予定の場所に基づいて、アドビが一部のバックエンド設定を判断するのに役立ちます。

* **Webサイト**:Adobe AnalyticsをWebサイト用に実装する場合。
* **ネイティブモバイルアプリ**:モバイルアプリ用にのみAdobe Analyticsを実装する場合。
* **両方**:このレポートスイートにWebサイトとモバイルアプリの両方のデータが含まれる場合。

### 業種

主なビジネスモデルを指定します。 この設定は、主なビジネスモデルに基づいて、一部の変数の名前と設定を事前設定する際に役立ちます。

### データレイヤー

デー [タレイヤーは](data-layer.md) 、実装で使用されるすべての変数を1つの役に立つ場所にまとめたJavaScriptオブジェクトです。 See [Data layers](data-layer.md) for more information.

### データリポジトリ

レポートスイートにわかりやすい名前を付けます。 レポートスイートID(RSID)は、わかりやすい名前とログイン会社名に基づいて自動的に生成されます。

### タイムゾーン

アドビがレポートスイートの正しいタイムゾーンを検出したことを確認します。

### 予想日別ページビュー数

Webサイトやアプリが1日に受けるトラフィック量を予測します。 この情報により、アドビは適切な量の処理リソースをレポートスイートに割り当てることができます。

### ベース通貨

レポートスイートが金額を保存する通貨を決定します。

> [!IMPORTANT] 特に売上高に関するレポート要件がある場合は、正しい通貨を入力してください。 データ収集の開始後にベース通貨を変更するのは困難です。

## 実装リソース

レポートスイートの作成後、実装を続行するには、次の2つのオプションのいずれかを選択します。

* **Adobe Experience Platform Launchに移動**:実装を設定し、デプ [ロイコードをダウンロードするため](https://launch.adobe.com) 、launch.adobe.comにリンクします。 [Launch による実装](../launch/overview.md)を参照してください。ほとんどの場合、「起動」の使用をお勧めします。
* **導入コードのダウンロード**:手動でJavaScriptを実装する場合に、JavaScriptファイルをダウンロードするための直接リンクを提供します。 [JavaScript 版 AppMeasurement](../js/overview.md) を参照してください。
