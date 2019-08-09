---
description: 必要なすべての Web サイトの更新をおこなったら、Charles*、Chrome Developer Tools または Firebug* などのネットワークトラフィックビューアを使用して、DFA が Adobe コレクションサーバーと通信していることを確認できます。
keywords: DFA
seo-description: 必要なすべての Web サイトの更新をおこなったら、Charles*、Chrome Developer Tools または Firebug* などのネットワークトラフィックビューアを使用して、DFA が Adobe コレクションサーバーと通信していることを確認できます。
seo-title: DFA 統合の成功の確認
solution: Analytics
title: DFA 統合の成功の確認
topic: Data Connectors
uuid: d658cd7c-6377-439a-850c- eca8c41f970
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# DFA 統合の成功の確認{#confirming-a-successful-dfa-integration}

必要なすべての Web サイトの更新をおこなったら、Charles*、Chrome Developer Tools または Firebug* などのネットワークトラフィックビューアを使用して、DFA が Adobe コレクションサーバーと通信していることを確認できます。

DFA 対応 `s_code.js` ファイルをデプロイしたら、ネットワークトラフィックビューアを使用して、DFA と Adobe データコレクションサーバーの間のリクエストを表示します。以下を確認します。

* A request to DFA's `fls.doubleclick.net/json` service. このサービスは、使用している DFA のバージョンに応じて応答が異なる可能性があります。DFA 統合バージョン 1.5 の場合：

   * [!DNL ad.doubleclick.net] への HTTP 302 リダイレクト。これは、広告訪問者に関する情報を含む応答に Location: タグを送信します。
   * This Location tag causes a redirect to [!DNL integrate.112.2o7.net/dfa_echo]. このサービスは、広告訪問者に関する情報を JSON（JavaScript Object Notation）エンコードされた文字列に変換します。このデータは、200 OK HTTP 応答で返されます。

* DFA 統合バージョン 2.0（アドバンス広告配信が有効）の場合：

   * [!DNL fls.doubleclick.net] が 200 OK で直接返されます。

どちらの場合も、成功リクエストは、パラメーター vX（X はビュースルー eVar 番号）を含む Adobe データコレクションサーバーへのリクエストになります。このパラメーターの値は、DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX という形式を取ります。この文字列には、現在の訪問者の最後のクリックおよび最後のインプレッションに関するデータが含まれています。
