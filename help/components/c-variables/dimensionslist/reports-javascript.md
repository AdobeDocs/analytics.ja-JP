---
description: デバイスで JavaScript が有効、無効、不明のいずれであるかに基づいて指標を表示します。
title: JavaScript サポート
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# JavaScript サポート

デバイスで JavaScript が有効、無効、不明のいずれであるかに基づいて指標を表示します。

>[!NOTE]2016 年 11 月始めには、モバイルデバイスで JavaScript が常に *`disabled / unidentified`* とリストされる制約を削除することを予定しています。

JavaScriptレポートは、生データのjavascript列に対応します。

javascriptは訪問レベルのフィールドなので、訪問の最初のヒットの値を保持します。 javascript列は、j_jscript列の最初の値に基づきます(visit_転送者が訪問の最初の転送者のみを保持するのと同様)。

j_jscriptは、Adobe Analyticsイメージリクエストのパラメーターjから入力されます。

次に例を示します。

| ヒット | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

その結果、訪問中のある時点でJavaScriptバージョンが指定されていても問題ありません。最初のヒットにj_jscriptの値が含まれていないので、常にJavaScriptではないと表示されます。
