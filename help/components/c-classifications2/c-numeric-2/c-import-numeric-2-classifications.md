---
description: インポートおよびエクスポートファイルには、それぞれの数値 2 分類に対して 6 つの列が含まれています。
seo-description: インポートおよびエクスポートファイルには、それぞれの数値 2 分類に対して 6 つの列が含まれています。
seo-title: 数値2分類のインポート
solution: Analytics
subtopic: '分類      '
title: 数値2分類のインポート
topic: 管理ツール
uuid: 82a3034c- e002-4991-900f-22dd45d54910
translation-type: tm+mt
source-git-commit: 49e149fe57d5d66b8eda22b1bdf60e7c6200761c

---


# 数値2分類のインポート

>[!IMPORTANT]
>
>数値 2 分類および日付分類をインポートする機能が廃止されます。この変更は 2019 年 7 月のメンテナンスリリースから有効になります。「Numeric（数値）」列または「Date-Enabled（日付）」列がインポートファイルにある場合、それらの値は警告なく無視され、そのファイル内の他のすべてのデータは通常どおりインポートされます。インポート済みの既存の分類は、通常の分類ワークフローで引き続きエクスポートでき、レポートで使用できます。

インポートおよびエクスポートファイルには、それぞれの数値 2 分類に対して 6 つの列が含まれています。

次の定義は、数値 2 分類の名前が「MyCost」であることを前提としています。

**~MyCost：**&#x200B;行を説明する名前。

**~ MyCost^~id~:** 既存の行を編集するためのID。新しい行を追加した場合、この ID は空白です。分類マネージャーからエクスポートすると、ID が自動的に割り当てられます。

**~MyCost^~value~: **The value for the row. レート（rate）列が固定値の場合、この値は期間全体で配分されるフラット値になります。レート（rate）列がイベントの場合、この値はイベントに対する乗数になります。このエントリにコンマを含めないでください。

**~ MyCost^~period~:** この行が対応する期間。開始日と終了日をダッシュで区切って含める必要があります。ダッシュの前後には空白を挿入する必要があります。定義は、次のようにフォーマットする必要があります。

YYYY/MM/DD - YYYY/MM/DD

**~ MyCost^~rate~:**[!UICONTROL Value] 列に乗算するイベントです。有効値は次のとおりです。

* fixed - 期間中のフラット値であることを示すために使用します。
* revenue
* order
* unit
* scopen
* scviews
* instance
* click
* checkout
* scadd
* scremove
* event1
* event2
* etc

**~ MyCost^~ヒンジ~:** 分類中に値を配布するために使用するイベントです。This value is often the same as [!UICONTROL ~MyCost^~rate~], unless you are using [!UICONTROL fixed]. The valid values for this column are identical to that of [!UICONTROL ~MyCost^~rate~], with the addition of [!UICONTROL none].
