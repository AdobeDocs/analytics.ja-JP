---
description: Adobe Analytics 用にデータを収集する方法を説明します。
subtopic: Get started
title: データ収集について
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 34a7be55-519a-4e04-95a3-99b0f6e04b3e
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 98%

---

# データ収集について

Adobe Analytics 用にデータを収集する方法を説明します。

大まかなデータ収集プロセスフローは次のようになります。

![](assets/data_collection.png)

1. 訪問者はデータ収集コードが含まれる Web ページを訪問します。
1. ページをロードすると、データ収集コードによってイメージリクエスト（Web ビーコンと呼ばれます）がアドビデータ収集サーバーに送信されます。イメージリクエストには、Web サイトでの訪問者のインタラクションを収集するためのデータが含まれます。
1. アドビではデータをレポートスイートに保存します。ログインしてレポートスイートデータにアクセスし、Web サイトでの訪問者のアクティビティに関するレポートを生成できます。

データの収集は非常に短時間で行われるので、ページロード時間に影響しません。ブラウザーの「**更新**」または「**戻る**」ボタンのクリックによるページビューも収集されます。ページがブラウザーキャッシュから取得された場合でも、JavaScript コードが実行されます。

デフォルトのホストグループを変更する方法については [Analytics でのデータ収集](/help/import/home.md)を参照してください。
