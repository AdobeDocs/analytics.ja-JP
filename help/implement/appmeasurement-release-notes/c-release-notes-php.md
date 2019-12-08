---
description: 'null'
subtopic: Release notes
title: PHP
topic: Developer and implementation
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# PHP{#php}

> [!NOTE]ライブラリの現在のバージョンを検索するには、デバッグログを有効にしてください。

## バージョン 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

リリース日：**2014 年 8 月**

* 今後追加される機能をサポートするために、コードの内容を一部変更しました。

## バージョン 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

リリース日：**2012 年 7 月**

* IIS の $_SERVER['HTTPS'] に "off" が返されたときのチェック機能を追加しました。このチェックがない場合、IE でブール関数 ((bool)$_SERVER['HTTPS']) に型キャストすると、リクエストが HTTP を経由するか HTTPS を経由するかにかかわらず true が返されます。その結果、保護されていないページが保護された画像リクエストを実行しようとします。

## バージョン 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

PHP 1.1 用の Measurement Library には、バージョン 1.0 からの以下の更新が含まれています。

* GeoSegmentation の精度が向上しました（`sendFromServer` が有効な場合）。
* バグの修正により、`userAgent` 変数に追加できるようになりました。
* イメージビーコンに対応するモバイルブラウザーが増え、対応性が向上しました。
* モバイルが有効な場合、`imageDimensions` 変数のデフォルト値が 5x5 に設定されるようになりました。
* ボット検出リストを絞り込みました。
* `debugTracking` および `sendFromServer` が有効な場合にデバッグ情報（HTTP ヘッダー、応答、エラーなど）が追加されました。

* `debugFilename` 変数が追加されました（`sendFromServer` が有効な場合）。

* `pagename` も `pageURL` も設定されていない場合に pagename 変数のデフォルト値が `$_SERVER['SCRIPT_NAME']` に設定されます。

* PHP の CGI 実装が完全にサポートされます。
* パフォーマンス強化。

