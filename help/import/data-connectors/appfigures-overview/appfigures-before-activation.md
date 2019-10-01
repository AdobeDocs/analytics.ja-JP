---
description: この統合をアクティブ化する前に、Adobe Analytics®のデプロイメントと電子メールソフトウェアに対して、次の項目を確認します。
seo-description: この統合をアクティブ化する前に、Adobe Analytics®のデプロイメントと電子メールソフトウェアに対して、次の項目を確認します。
seo-title: この統合をアクティブ化する前に
title: この統合をアクティブ化する前に
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# この統合をアクティブ化する前に {#before-you-activate-this-integration}

この統合をアクティブ化する前に、Adobe Analytics®のデプロイメントと電子メールソフトウェアに対して、次の項目を確認します。

これにより、有効化の前に適切なベストプラクティスまたは前提条件が確実に実施され、最適で正常な統合が実現します。

## Adobe Analytics Requirements{#adobe-analytics-requirements}

Adobe Analyticsに関連する、このData Connectors統合に関する次の情報を確認します。

* **** レポートスイート固有：この統合はレポートスイートに固有であることをお勧めします。 統合をアクティブ化する前に、目的のレポートスイートが選択されていること、およびレポートスイートにデータが含まれていることを確認します。
* **** 利用可能で設定済みのAnalytics変数：この統合には、10件のカスタムイベントと1件のカスタムeVarが必要です。 詳しくは、 [Analytics統合変数を参照してください](appfigures-before-activation.md#analytics-integration-variables)。

* **** Liveデータで初期化されたレポートスイート：この統合用に新しいレポートスイートを作成する場合は、ライブトラッキングのappFigures要件を使用して、いくつかの（少なくとも1つのヒット）データを受け取っている必要があります。 ライブデータが記録されていない場合、レポートスイートは統合App storeデータを受け取る準備ができていません。

* **** App Storeとの既存の統合：この統合により、13か月間のデータが埋め戻されます。 以前のApp Storeデータプロバイダーとの重複を回避するには、appFiguresの担当者にお問い合わせください。 最後にデータを受け取った日を知らせます。 appFiguresは、それに従って裏込め期間を調整します。

## appFigures Requirements{#appfigures-requirements}

appFiguresに関連する、このdata connectors統合に関する次の情報を確認します。

* **** appFiguresの現在のお客様：この統合では、AdobeとappFiguresの両方のユーザーである必要があります。 現在appFiguresエンタープライズプランのユーザーでない場合は、統合ウィザードの完了に必要な情報は提供されません。 詳しくは、Web上のappFiguresを参照してください。
* **** appFiguresアカウントキー：appFigures Data Connectorをアクティブにするには、appFiguresアカウントキーが必要です。 このアカウントキーは「アドオン」セクションで生成できます。 詳細につい [ては、「統合の設定](../appfigures-overview/t-appfigures-integration.md) 」を参照してください。

* **Data Finalization**:ダウンロード、販売、およびランキング情報は、過去7日間の毎日同期されます。 7日間のデータが最終的と見なされ、更新されなくなります。

## 価格{#pricing}

このData Connectors統合には、価格に関する考慮事項が含まれています。

詳しくは以下のセクションで説明されています。

### アドビの価格に関する考慮事項 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

現在、この統合を有効にする料金はありません。 ただし、データソースのインポートが原因で、サーバーコールが若干増加する場合があります。

### appFiguresの価格に関する考慮事項 {#section-c6afad08c34b43e3a7a3637eea3328c3}

現在、この統合に関連する料金は発生しません。 この統合は、現在、エンタープライズのお客様のみご利用いただけます。 詳しく [は、appFigures](https://appfigures.com/support/contact) にお問い合わせください。

## Analytics Integration Variables{#analytics-integration-variables}

appFigures用のdata connectors統合では、Analytics変数を使用して様々なappFigures指標を追跡します。

次の表に、appFigures統合用に自動的にアクティブ化されるAnalytics変数を示します。

### 必須変数 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>この統合では、アプリストアデータに専用の変数を使用するので、カスタムコマース変数やイベントを割り当てる必要はありません。

| 変数の種類 | 名前 | セット方法 | 説明 |
|---|---|---|---|
| eVar | App Store オブジェクト ID | appFiguresからインポート。 | このeVarを、訪問の有効期限、最新の配分、基本的な下位関係で設定します。 |
| event（数値） | App Store でのダウンロード数 | appFiguresからインポート。 | モバイルアプリケーションダウンロード数。 |
| event（数値） | App Storeでの購入（アプリ内） | appFiguresからインポート。 | アプリ内課金および購読の数。 |
| event（数値） | App Store ランク | appFiguresからインポート。 | 平均appFigures計算指標を定義するために使用します。 直接使用されません。 |
| event（数値） | App Store Rank Divisor | appFiguresからインポート。 | 平均appFigures計算指標を定義するために使用します。 直接使用されません。 |
| event（数値） | App Store 評価 | appFiguresからインポート。 | 平均appFigures計算指標を定義するために使用します。 直接使用されません。 |
| event（数値） | App Store 評価の基準値 | appFiguresからインポート。 | 平均appFigures計算指標を定義するために使用します。 直接使用されません。 |
| イベント（通貨） | App storeの売上高（アプリ内） | appFiguresからインポート。 | アプリ内の売上金額からストア料金を引いた額。 |
| イベント（通貨） | App storeの売上高（1回限り） | appFiguresからインポート。 | アプリの購入からストアの費用を引いた合計売上高。 |
| イベント（通貨） | App Storeのロイヤルティ（アプリ内） | appFiguresからインポート。 | 未使用 |
| イベント（通貨） | App Storeのロイヤルティ（1回限り） | appFiguresからインポート。 | 未使用 |
