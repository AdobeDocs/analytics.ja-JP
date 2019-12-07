---
description: JavaScript 変数で使用できない文字および文字列です。
keywords: Analytics Implementation
subtopic: Variables
title: JavaScript での無効な文字
topic: Developer and implementation
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript での無効な文字

JavaScript 変数で使用できない文字および文字列です。

* タブ（0x09）
* キャリッジリターン（0x0D）
* 改行（0x0A）
* コード番号が 127 以降の ASCII 文字（マルチバイト文字を有効化し、*`charSet`* を適切に設定している場合は除く）
* HTML タグ（例：<b></b> や &amp;#153）

多くの変数（特に製品、階層およびイベント変数）には、他にも制限や構文上の要件があります。個々の変数の制限および構文上の要件については、*`s_account`* 変数パラメーターに対応するセクションを参照してください。
