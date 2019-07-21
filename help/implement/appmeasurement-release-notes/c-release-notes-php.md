---
description: 'null'
seo-description: 'null'
seo-title: PHP
solution: Analytics
subtopic: リリースノート
title: PHP
topic: 開発者と導入
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# PHP{#php}

>[!NOTE]
>
>現在のライブラリバージョンを検索するには、デバッグログを有効にします。

## バージョン 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

リリース日：**2014 年 8 月**

* 今後追加される機能をサポートするために、コードの内容を一部変更しました。

## バージョン 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

リリース日：**2012 年 7 月**

* Added a check for the "off" returned for the $_SERVER['HTTPS'] in IIS. Without this check, typecasting to boolean ((bool)$_SERVER['HTTPS']) returned true in IE whether the request was made through HTTP or HTTPS. その結果、保護されていないページが保護された画像リクエストを実行しようとします。

## バージョン 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

PHP 1.1 用の Measurement Library には、バージョン 1.0 からの以下の更新が含まれています。

* GeoSegmentation の精度が向上しました（`sendFromServer` が有効な場合）。
* バグの修正により、`userAgent` 変数に追加できるようになりました。
* イメージビーコンに対応するモバイルブラウザーが増え、対応性が向上しました。
* モバイルが有効な場合、`imageDimensions` 変数のデフォルト値が 5x5 に設定されるようになりました。
* ボット検出リストを絞り込みました。
* `debugTracking` および `sendFromServer` が有効な場合にデバッグ情報（HTTP ヘッダー、応答、エラーなど）が追加されました。

* Added the `debugFilename` variable (when `sendFromServer` is enabled).

* The pagename variable defaults to `$_SERVER['SCRIPT_NAME']` when neither `pagename` nor `pageURL` are set.

* PHP の CGI 実装が完全にサポートされます。
* パフォーマンス強化.

