---
description: Data Warehouseには、訪問者IDのリストを抽出できる機能が用意されています。 これらのIDはCookie IDではなく、コンバージョン変数のひとつに取り込むIDです。 この情報を取得する方法は他にもありますが、次の例はData Warehouse リクエストを生成するためのショートカットです。
title: 使用事例 - 訪問者 ID の抽出
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
TQID: 'https://experienceleague.adobe.com/CUpKcu-jVNn77bkWM2mJvlLxYMyvfpRt4o-maC7tUBA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 8%

---

# 使用事例 - 訪問者 ID の抽出

Data Warehouseには、訪問者IDのリストを抽出できる機能が用意されています。 これらのIDはCookie IDではなく、コンバージョン変数のひとつに取り込むIDです。 この情報を取得する方法は他にもありますが、次の例はData Warehouse リクエストを生成するためのショートカットです。

例えば、顧客や見込み顧客にマーケティングメールを送信するとします。 これらの電子メール受信者はそれぞれ、電子メールシステムで一意のID （*`EMAIL Contact ID`*&#x200B;など）を持っています。 電子メールを設定すると、連絡先が電子メールを受け取り、リンクの1つをクリックすると、訪問者はキャンペーン IDと一意の電子メール連絡先IDを持つweb サイトに到達します。 例えば、電子メールリンクは次のように解決されます。

```js
https://www.example.com/?cid=springmailblast&mid=1363660158
```

コンバージョン変数（eVar）でこれらを設定すると、各電子メールのパフォーマンス（キャンペーン ID）と、各電子メール受信者がサイトを訪問した頻度（電子メール連絡先ID）を確認できます。

これらのIDをキャプチャしていると仮定します。 多くのマーケターは、web サイトの行動をセグメンテーションし、特定の条件を満たしたオーディエンスにリマーケティングできるかどうかを確認したいと考えています。 例えば、電子メールからサイトにアクセスし、web サイトのフォームを閲覧（または完了）したすべての電子メール受信者に対して、リマーケティング電子メールを送信することができます。 これを行うには、特定のフォームに入力するユーザーの電子メール連絡先IDを特定する方法を見つけます。

これを行う方法の1つは、コンバージョン下位関係レポートを使用して、フォーム ID eVarの値をEMAIL Contact ID eVarで分類することです。 ただし、Data Warehouseを使用してこれを行うには、事前定義済みの機能を使用できます。 この機能を使用すると、どのeVarに一意のユーザーID （この場合はメール連絡先ID）が保存されているかを確認でき、データウェアハウスを使用してそれらのIDを簡単に抽出できます。 この機能により、対象となるユニーク訪問者 ID を取り込む data warehouse リクエストを自動的に作成できます。
