---
description: Web ログデータソースから、標準の Web サーバーログファイルをインポートできます。
subtopic: Data sources
title: Web ログ
topic-fix: Developer and implementation
uuid: a0efed57-6d1b-43d8-97ce-dc31009805e0
exl-id: 11c4f21a-de07-436e-a05e-ab6769cb3e21
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 100%

---

# Web ログ

Web ログデータソースから、標準の Web サーバーログファイルをインポートできます。

次の一般的な Web サーバーログタイプがサポートされます。

| 列名 | 説明 |
|--- |--- |
| NCSA 共通ログ | Apache 既定 |
| NCSA 拡張（統合） | Apache |
| W3C 拡張ログ | IIS 4.0 以降で使用 |
| Microsoft IIS ログ | IIS 3.0 以前で使用 |

データソースで処理される主要なログファイルフィールドには、IP アドレス、リクエストの日付／時間、URL などがあります。NCSA 拡張フォーマットなどの場合、リファラーやユーザーエージェントのフィールドも処理されることが稀にあります。

標準のマーケティングレポートを使用して Web ログデータを表示し、ページビュー数、訪問回数、訪問者数を確認することができます。レポート指標は主に cookie に基づいており、Web サーバーログは IP アドレスに基づいているので、アドビでは Web サーバーログをこのインポート用に特別に設定した個別のレポートスイートにインポートすることをお勧めします。

Web サーバーログファイルについて詳しくは、ご使用の Web サーバーのドキュメントを参照してください。
