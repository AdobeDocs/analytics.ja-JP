---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 8deec068fcea49f1183633826d5ce8271fb38a14

---



# s.useForcedLinkTracking

このフラグは、一部のブラウザーでの強制のリンクトラッキングを無効にするために使用します。強制のリンクトラッキングは、FireFox 20 以降および WebKit ブラウザーではデフォルトで有効になっています。

`useForcedLinkTracking` を有効にすると、一部のブラウザーで新しいページを開いたときにリンクトラッキングがキャンセルされることを防ぐために、AppMeasurement のデフォルトのリンク動作が上書きされます。AppMeasurement ファイルでは、リンクトラッキングを実行し、デフォルトのブラウザーのアクションを使用せずにナビゲーションイベントとして処理します。

JavaScript H.25.4（2013 年 2 月リリース）では、`useForcedLinkTracking` を有効にしたときに追跡されるリンクについて、次のような範囲制限が追加されました。自動強制のリンクトラッキングは、次の場合にのみ適用されます。

* `<A>` および `<AREA>` タグです。
* タグに `HREF` 属性が含まれている。
* `HREF` は `#`、`about:`、または `javascript:` で始まらない。
* `TARGET` 属性が設定不可、または `TARGET` で現在のウィンドウ（`_self`、`_top`、または `window.name` の値）を参照する必要がある。

デフォルト値 = `true`

## 例

`s.useForcedLinkTracking = false`
