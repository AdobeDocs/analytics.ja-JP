---
description: 計算指標および高度な計算指標は、既存の指標から作成できるカスタム指標です。
keywords: 計算指標;高度な計算指標
title: 計算指標および高度な計算指標
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: ht
source-wordcount: '552'
ht-degree: 100%

---

# 計算指標および高度な計算指標

計算指標および高度な計算指標は、既存の指標から作成できるカスタム指標です。

計算指標ツールを使用すると、指標を極めて柔軟に作成および管理できます。マーケター、製品マネージャーおよびアナリストは、[!DNL Analytics] の実装を変更することなくデータを照会できます。各 [!DNL Analytics] パッケージで利用可能なカスタム指標を次に示します。

* Adobe [!DNL Analytics] Foundation：計算指標
* [Adobe Analytics Select](https://www.adobe.com/jp/data-analytics-cloud/analytics/select.html)：計算指標 + 高度な計算指標
* [Adobe Analytics Prime](https://www.adobe.com/jp/data-analytics-cloud/analytics/prime.html)：計算指標 + 高度な計算指標
* [Adobe Analytics Ultimate](https://www.adobe.com/jp/data-analytics-cloud/analytics/ultimate.html)：計算指標 + 高度な計算指標

次に、計算指標と高度な計算指標の機能比較を示します。

| ビルダーのオプション | 計算指標 | 高度な計算指標 |
|---|---|---|
| [形式のタイプ（小数、時間、割合、通貨）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | ○ | ○ |
| [アトリビューションの変更（デフォルト、線形、パーティシペーションなど）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | ○ | ○ |
| [指標のタイプ（標準、合計）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | ○ | ○ |
| 基本的な演算子（可算、減算、乗算、除算） | ○ | ○ |
| [セグメントの適用](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | × | ○ |
| [基本的な関数（カウント、絶対値、平均など）](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | × | ○ |
| [高度な関数（回帰、if/then、t スコアなど）](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | × | ○ |

## 機能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

次のことが可能です。

* [!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 異常値検出]、[!UICONTROL 貢献度分析]をまたいで指標を作成します。
* 実装を変更せずに、レポート実行時に導出されるセグメント化された指標を作成します。これらの指標はセグメントに基づいているので、時系列で表示できます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [計算指標](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

* レポートスイート間で指標を共有する。つまり、新しく作成されたすべての指標は、同じログイン会社のすべてのレポートスイートに適用されます。
* （高度な計算指標のみ）指標のセグメント。例えば、初回セッションの訪問者数を含む、「初回訪問者数」の指標を作成できます。

* （高度な計算指標のみ）データをわかりやすく記述するための統計関数を組み込む。例えば、レポート内の項目数をカウントしたり、各項目の標準偏差の数を追加したりできます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [セグメントのセグメント化計算指標](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## 制限事項 {#section_CB878B02451541D68A68B508D4DBD19A}

一部の [!DNL Analytics] の機能では、イベントは使用できますが、計算指標は使用できません。

* [!UICONTROL Analysis Workspace ][!UICONTROL のフォールアウト]
* [!UICONTROL Analysis Workspace のコホート分析]
* [!UICONTROL Data Warehouse]
* [!UICONTROL セグメント]
* [!DNL Analytics] for [!DNL Target]

## ツール {#section_D65E9C067E9C45E1A50DD30F50561BB2}

ここでは、[!UICONTROL 計算指標]ツールの概要を簡単に示します。

| ツール | 機能 |
|--- |--- |
| 計算指標ビルダー | <ul><li>高度な配分モデルを使用した計算指標および高度な計算指標を作成する。</li><li>指標の数式にセグメントをインラインで追加する</li><li>同じレポート内のセグメントを比較する。例えば、各地域における訪問者と海外での訪問者を比較します。</li><li>統計関数を使用する</li><li>指標の詳細な説明を指定する（指標の用途や指標を使用する（または使用しない）場所を示します）</li><li>新しい指標に定義をコピーする</li><li>インラインで指標をプレビューする</li><li>指標の両極性を設定する。これは、指定されたカスタムイベント（指標）が発生した場合に、それが良いか悪いかを示します</li><li>指標にタグ付けする</li></ul> |
| 計算指標マネージャー | <ul><li>他のユーザーと指標を共有する&lt;/li<li>指標を承認して管理する</li><li>ユーザーが検索しやすいように指標を管理（タグ付け）する</li><li>指標を削除する</li><li>指標の名前を変更する</li></ul> |
| 指標セレクターパネル | このパネルを使用すると、指標を検索したり、指標をレポートに追加または適用したりできます。また、並べ替え順序を変更することもできます（オプション：アルファベット順、推奨順、頻繁に使用した順、最近使用した順）。さらに、レポートスイートをフィルタリングして、特定のレポートスイートで作成された指標のみを表示できます。この指標セレクターにアクセスするには、レポートの左側の指標アイコンをクリックします。 |
| 計算指標の API | Adobe Analytics 2.0 API セットの一部。 |
