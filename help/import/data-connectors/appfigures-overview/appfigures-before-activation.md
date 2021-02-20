---
description: この統合をアクティブ化する前に、Adobe Analytics® のデプロイメントとお使いの電子メールソフトウェアに対して、次の項目を確認します。
title: この統合をアクティブ化する前に
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 100%

---


# この統合をアクティブ化する前に {#before-you-activate-this-integration}

この統合をアクティブ化する前に、Adobe Analytics® のデプロイメントとお使いの電子メールソフトウェアに対して、次の項目を確認します。

これにより、アクティブ化の前に適切なベストプラクティスまたは前提条件が確実に実施され、最適で正常な統合が実現します。

## Adobe Analytics の要件 {#adobe-analytics-requirements}

この Data Connectors 統合について、Adobe Analytics と関係のある次の情報を確認します。

* **レポートスイート固有：**&#x200B;この統合は、レポートスイートに固有です。統合をアクティブ化する前に、目的のレポートスイートが選択されていること、およびレポートスイートにデータが含まれていることを確認します。
* **利用可能な設定済みの Analytics 変数：**&#x200B;この統合には、10 件のカスタムイベントと 1 件のカスタム eVar が必要です。[Analytics 統合変数](appfigures-before-activation.md#analytics-integration-variables)を参照してください。

* **ライブデータで初期化されたレポートスイート：**&#x200B;この統合用に新しいレポートスイートを作成する場合は、ライブトラッキングの appFigures 要件を使用して、いくつかの（1 ヒット以上の）データを受け取っている必要があります。ライブデータが記録されていない場合、レポートスイートは統合 App Store データを受け取る準備ができていません。

* **App Store との既存の統合：**&#x200B;この統合により、13 ヶ月間のデータがバックフィルされます。以前の App Store データプロバイダーとの重複を回避するには、appFigures の担当者にお問い合わせください。最後にデータを受け取った日を知らせます。appFigures は、それに従ってバックフィル期間を調整します。

## appFigures の要件 {#appfigures-requirements}

この Data Connectors 統合について、appFigures と関係のある次の情報を確認します。

* **appFigures の現在のお客様：**&#x200B;この統合では、アドビと appFigures の両方のユーザーである必要があります。現在 appFigures エンタープライズプランのユーザーでない場合、統合ウィザードの完了に必要な情報は提供されません。詳しくは、Web で appFigures にアクセスしてください。
* **appFigures アカウントキー：** appFigures Data Connector をアクティブ化するには、appFigures アカウントキーが必要です。このアカウントキーは「アドオン」セクションで生成できます。詳細については、「[統合の設定](../appfigures-overview/t-appfigures-integration.md)」を参照してください。

* **データの終了処理**：ダウンロード、販売、およびランキング情報は、過去 7 日間について毎日同期されます。7 日間のデータが最終版と見なされ、それ以降は更新されません。

## 価格 {#pricing}

この Data Connectors 統合には、価格に関する考慮事項が含まれています。

詳しくは以下のセクションで説明されています。

### アドビの価格に関する考慮事項 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

現在、この統合をアクティブ化するための料金は発生しません。ただし、データソースの読み込みにより、サーバーコールが若干増加する場合があります。

### appFigures の価格に関する考慮事項 {#section-c6afad08c34b43e3a7a3637eea3328c3}

この統合に関連する料金は発生しません。この統合は、現在、エンタープライズのお客様のみがご利用いただけます。詳しくは、[appFigures](https://appfigures.com/support/contact) にお問い合わせください。

## Analytics 統合変数 {#analytics-integration-variables}

appFigures 用 Data Connectors 統合は、Analytics 変数を使用してさまざまな appFigures 指標を追跡します。

次の表に、appFigures 統合で自動的に有効となる Analytics 変数を示します。

### 必須変数 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>この統合では、アプリストアデータに専用の変数を使用するので、カスタムコマース変数やイベントを割り当てる必要はありません。

| 変数の種類 | 名前 | 母集団メソッド | 説明 |
|---|---|---|---|
| eVar | アプリストアオブジェクト ID | appFigures から読み込まれます。 | 訪問の有効期限、最新の配分、基本的な下位関係を使用して、この eVar を設定します。 |
| イベント（数値） | アプリストアでのダウンロード数 | appFigures から読み込まれます。 | モバイルアプリケーションダウンロード数。 |
| イベント（数値） | アプリストアでの購入（アプリ内） | appFigures から読み込まれます。 | アプリ内課金およびサブスクリプションの数。 |
| イベント（数値） | アプリストアランク | appFigures から読み込まれます。 | 平均 appFigures 計算指標の定義に使用します。直接は使用しません。 |
| イベント（数値） | アプリストアランクの約数 | appFigures から読み込まれます。 | 平均 appFigures 計算指標の定義に使用します。直接は使用しません。 |
| イベント（数値） | アプリストアの評価 | appFigures から読み込まれます。 | 平均 appFigures 計算指標の定義に使用します。直接は使用しません。 |
| イベント（数値） | アプリストアの評価の約数 | appFigures から読み込まれます。 | 平均 appFigures 計算指標の定義に使用します。直接は使用しません。 |
| イベント（通貨） | アプリストアの売上高（アプリ内） | appFigures から読み込まれます。 | アプリ内の売上金額から店舗手数料を引いた額。 |
| イベント（通貨） | アプリストアの売上高（1 回限り） | appFigures から読み込まれます。 | アプリケーションの購入から店舗手数料を引いた合計売上高。 |
| イベント（通貨） | アプリストアのロイヤルティ（アプリ内） | appFigures から読み込まれます。 | 未使用 |
| イベント（通貨） | アプリストアのロイヤルティ（1 回限り） | appFigures から読み込まれます。 | 未使用 |
