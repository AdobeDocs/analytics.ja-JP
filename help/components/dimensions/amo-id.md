---
title: AMO ID
description: Adobe Advertising統合で使用されるAdobe Media Optimizer ID。
feature: Dimensions
exl-id: 90642896-43dd-4ac0-bfb8-7fe34c0e0302
TQID: 'https://experienceleague.adobe.com/SzHWYAzd9iYcd5AU86TVL6Bfca4UsuijV141jBuS0y8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 793
ht-degree: 3%

---

# AMO ID

**[!UICONTROL AMO ID]**&#x200B;は、Adobe Advertising統合で使用される連結されたIDのコレクションです。 このディメンションに保存された値は、Analytics レポートで使用するために、人間が判読可能な個別の分類ディメンションに自動的に整理されます。 ディメンションは、[Analytics for Advertising](https://experienceleague.adobe.com/ja/docs/advertising/integrations/analytics/overview)統合を有効にすると自動的に作成されます。

## このディメンションへのデータ入力

このディメンションは、複数の方法で値を収集します。

* クリックスルートラフィックの場合、データは[&#x200B; ページ URL](page-url.md)の`s_kwcid` クエリ文字列パラメーターから収集されます。通常は、広告駆動型トラフィックがサイトに入るページ上に収集されます。
* クリックスルートラフィックは、URLにトラッキングコードが含まれていない場合にもキャプチャできますが、Adobe Advertising JavaScriptでは、前の2分以内にクリックが検出されます。
* サポートされているビュースルートラフィックの場合、Adobe Advertisingはバックエンドの値を補足ID （`SDID`）を使用して補完します。

## ディメンション項目

Dimensionの項目には、AMO IDが含まれます。これは`s_kwcid`値とも呼ばれます。 正確なフォーマットは、トラフィックがDSPから送信されたか、Search, Social, &amp; Commerceから送信されたかによって異なります。 AMO IDはEF IDよりも詳細ではないため、主にAnalyticsでのAdobe Advertising メトリクスの分類と取り込みに使用されます。

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**：表示チャネルを示します。
* **`ad key`**: Adobe Advertisingが生成した広告の英数字ID。
* **`placement key`**: プレースメントのAdobe Advertising生成の英数字ID。

値の例：

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### Search, Social, &amp; Commerce

検索、ソーシャル、およびCommerce AMO IDは`AL`で始まり、広告主のユーザーID、広告ネットワークアカウント ID、ネットワーク固有のIDが続きます。 共有された広告ネットワークアカウント IDには、次のものが含まれます。

* **`3`**: Google Ads
* **`10`**: Microsoft Advertising
* **`45`**: Meta
* **`86`**: Yahoo! ディスプレイネットワーク
* **`87`**: ネイバー
* **`88`**: Baidu
* **`90`**: Yandex
* **`94`**: Yahoo! Japan Ads
* **`105`**: Yahoo Native （非推奨）
* **`106`**: Pinterest （非推奨）

#### Google 広告

Google広告では、2つの関連フォーマットが使用されています。 新しいアカウントには、キャンペーン IDと広告グループ IDを含めることができます。これにより、Performance Maxおよびドラフト/実験キャンペーンのキャンペーンレベルおよび広告グループレベルのレポートがサポートされます。

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**: Google Ads クリエイティブ ID。
* **`matchtype`**: キーワードの一致タイプ （`e`は正確、`p`はフレーズ、`b`はブロード）。
* **`placement`**：広告がクリックされたドメイン。
* **`network`**: クリックが発生したネットワーク （`g` Google検索、検索パートナーの`s`、ディスプレイの`d`）。
* **`product partition`**：製品広告の製品グループ ID。
* **`keyword`**：検索サイトでキーワードをトリガーするか、コンテンツサイトでキーワードを一致させます。
* **`campaign id`**: Google Ads キャンペーン ID （存在する場合）。
* **`ad group id`**:Google Ads広告グループ ID （存在する場合）。

動的検索広告の場合、キーワードフィールドに自動ターゲットが入力されます。

例：

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**: Microsoft Advertising クリエイティブ ID。
* **`keyword/order item id`**: Microsoft Advertising キーワード ID。
* **`campaign id`**: Microsoft Advertising キャンペーン ID。
* **`ad group id`**: Microsoft Advertising広告グループ ID。

従来のMicrosoft形式は、移行されていない一部のアカウントでも引き続き使用できます。

例：

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### 百度

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**: Baidu クリエイティブ ID。
* **`placement`**：広告がクリックされたWeb サイト。
* **`keyword id`**: Baidu キーワード ID。

#### Yahoo! は、 Japan Ads

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**: Yahoo! Japan Ads creative ID。
* **`matchtype`**: キーワード一致タイプ （`be`個の正確な語句、`bp`個の語句、`bb`個の幅広い語句）。
* **`network`**: クリックが発生したネットワーク （`n` ネイティブ、`s`検索）。
* **`keyword`**: キーワードをトリガーしています。

#### Yandex

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**: Yandex クリエイティブ ID。
* **`source type`**：広告が表示されたサイトタイプ （`b`検索、`c` コンテキスト/コンテンツ、`ct` カテゴリー）。
* **`phrase id`**: Yandex キーワード ID。

## 分類

Advertising[&#128279;](https://experienceleague.adobe.com/ja/docs/advertising/integrations/analytics/overview)のAnalytics統合を有効にすると、次の分類が自動的に作成されます。 分類値は、統合によって自動的に維持されます。

| 分類 | 説明 | DSP | 検索，<br> ソーシャル，&amp;<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL アカウント]** | アカウント名。 | &check; | &check; |
| **[!UICONTROL 広告の表示URL]** | 広告に表示されるURL。 | | &check; |
| **[!UICONTROL 広告の説明]** | 広告説明（DSP）または広告本文（検索、ソーシャル、Commerce）。 | &check; | &check; |
| **[!UICONTROL 広告宛先URL]** | 広告の宛先URL。 | | &check; |
| **[!UICONTROL 広告グループ]** | 広告グループ名。 | | &check; |
| **[!UICONTROL 広告プラットフォーム]** | 広告のDSPまたは検索エンジン名。 | &check; | &check; |
| **[!UICONTROL 広告タイトル]** | 広告の種類（DSP）または広告タイトル（検索、ソーシャル、Commerce）。 | &check; | &check; |
| **[!UICONTROL 広告の種類]** | 広告タイプ（`text`、`video`、`display`、`native`など）。 | &check; | &check; |
| **[!UICONTROL AdCloud属性1]** -<br>**[!UICONTROL AdCloud属性5 &#x200B;]** | 将来のカスタム属性に予約されるプレースホルダー分類。 現在使用されていません。 | | |
| **[!UICONTROL Campaign]** | キャンペーン名。 | &check; | &check; |
| **[!UICONTROL Creative エクスペリエンス名]** | 広告インタラクションに関連付けられたクリエイティブエクスペリエンスの名前。テストまたはパーソナライゼーションで使用されるクリエイティブのバリエーションのグループを表します。 | &check; | |
| **[!UICONTROL Creative支店名]** | クリエイティブ実験内の特定のバリエーションまたはパスを表す、クリエイティブ体験内のブランチの名前。 | &check; | |
| **[!UICONTROL Creative支店ID]** | クリエイティブエクスペリエンス内のクリエイティブブランチに割り当てられた一意のID。 | &check; | |
| **[!UICONTROL Creative名]** | ユーザーに配信された特定の広告クリエイティブアセットの名前。 | &check; | |
| **[!UICONTROL Creative バリアント名]** | クリエイティブエクスペリエンスまたはブランチ内で使用されるクリエイティブの特定のバリエーションの名前。 | &check; | |
| **[!UICONTROL キーワード]** | キーワード。 | | &check; |
| **[!UICONTROL キーワード一致タイプ]** | キーワードと一致タイプ。 | | &check; |
| **[!UICONTROL ランディングタイプ]** | ランディングページのエントリがビュースルーまたはクリックスルーのどちらであったか。 | &check; | &check; |
| **[!UICONTROL 一致タイプ]** | 検索の一致タイプ。 | | &check; |
| **[!UICONTROL ネットワーク]** | RTB （DSP）またはアドネットワーク名（検索、ソーシャル、Commerce）。 | &check; | &check; |
| **[!UICONTROL 最適化]** | パッケージ名（DSP）またはポートフォリオ名（検索、ソーシャル、Commerce）。 | &check; | &check; |
| **[!UICONTROL プレースメント]** | プレースメント名。 | &check; | |
| **[!UICONTROL 製品ターゲット]** | 製品リスト広告の製品ターゲット。 | | &check; |
