---
description: Data Warehouse には、訪問者 ID のリストを抽出できる機能があります。これらの ID は、cookie ID ではなく、コンバージョン変数のいずれかで取得する ID です。この情報を得るための方法はいくつかありますが、次の例は Data Warehouse リクエストを生成するためのショートカットを示しています。
title: 使用事例 - 訪問者 ID の抽出
feature: Admin Tools
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
source-git-commit: 68389772dec0420a66767bb0af9dea3122e1cb0f
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 100%

---

# 使用事例 - 訪問者 ID の抽出

Data Warehouse には、訪問者 ID のリストを抽出できる機能があります。これらの ID は、cookie ID ではなく、コンバージョン変数のいずれかで取得する ID です。この情報を得るための方法はいくつかありますが、次の例は Data Warehouse リクエストを生成するためのショートカットを示しています。

仮に、貴社が顧客および見込み顧客にマーケティング用の電子メールを送信しているとします。社内の電子メールシステムには、それぞれの電子メール受信者に一意の ID が保存されています。（例えば、*`EMAIL Contact ID`*).電子メールの設定では、連絡先が電子メールを受け取り、その中にあるリンクをクリックすると、キャンペーン ID と固有の EMAIL Contact ID を使って貴社の Web サイトを訪問するようになっています。例えば、電子メールに次のようなリンクがあるとします。

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

これをコンバージョン変数（eVar）に設定すると、それぞれの電子メールの効果（キャンペーン ID を通して）および電子メールの各受信者がサイトを訪問した頻度（EMAIL Contact ID を通して）を確認できます。

これらの ID を取得するとします。ほとんどのマーケティング担当者は、Web サイトでの行動をセグメント化して、特定の条件を満たす人に再マーケティングを試みます。例えば、電子メールからサイトを訪問して Web サイトのフォームを表示（または完了）したすべての電子メール受信者を対象に、再マーケティングの電子メールを送信することが考えられます。これを行うには、特定のフォームを完了した人の EMAIL Contact ID を識別する方法を見つける必要があります。

その 1 つの方法として、コンバージョン下位関係レポートを使って、Form ID eVar の値を EMAIL Contact ID eVar で分類するというものがあります。ただし、プレビルト機能では、Data Warehouse を使用してそれを行えるようになっています。この機能を使用すると、どの eVar が一意のユーザー ID を保存するかを指定でき（この場合は EMAIL Contact ID）、data warehouse を使用してそれらの ID を簡単に抽出できます。この機能により、対象となる一意の訪問者 ID を取り込む data warehouse リクエストを自動的に作成できます。