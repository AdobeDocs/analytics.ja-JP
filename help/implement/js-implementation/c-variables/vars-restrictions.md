---
description: JavaScript 変数で使用できない文字および文字列です。
keywords: Analytics の導入
seo-description: JavaScript 変数で使用できない文字および文字列です。
seo-title: 無効なJavaScript文字
solution: Analytics
subtopic: 変数
title: 無効なJavaScript文字
topic: 開発者と導入
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 無効なJavaScript文字

JavaScript 変数で使用できない文字および文字列です。

* タブ（0x09）
* キャリッジリターン（0x0D）
* 改行（0x0A）
* コード番号が 128 以降の ASCII 文字（マルチバイト文字を有効化し、*`charSet`* を適切に設定している場合は除く）
* HTML tags (e.g. <b></b> or &amp;#153)

多くの変数（特に製品、階層およびイベント変数）には、他にも制限や構文上の要件があります。個々の変数の制限および構文上の要件については、*`s_account`* 変数パラメーターに対応するセクションを参照してください。
