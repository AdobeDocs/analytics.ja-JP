---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8deec068fcea49f1183633826d5ce8271fb38a14

---



# s.useForcedLinkTracking

このフラグは、一部のブラウザーでの強制のリンクトラッキングを無効にするために使用します。強制のリンクトラッキングは、FireFox 20 以降および WebKit ブラウザーではデフォルトで有効になっています。

When `useForcedLinkTracking` is enabled, the AppMeasurement file overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. AppMeasurementファイルは、リンクトラッキングを実行し、デフォルトのブラウザーアクションを使用する代わりに、ナビゲーションイベントを手動で処理します。

JavaScript H.25.4（2013 年 2 月リリース）では、`useForcedLinkTracking` を有効にしたときに追跡されるリンクについて、次のような範囲制限が追加されました。自動強制のリンクトラッキングは、次の場合にのみ適用されます。

* `<A>` および `<AREA>` タグを参照してください。
* タグに `HREF` 属性が含まれている必要がある.
* The `HREF` can't start with `#`, `about:`, or `javascript:`.
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

デフォルト値 = `true`

## 例

`s.useForcedLinkTracking = false`
