---
description: Adobe Analytics 用にデータを収集する方法を説明します。
subtopic: Get started
title: データ収集について
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
feature: Reports & Analyticsの基礎知識
role: Business Practitioner, Administrator
exl-id: 34a7be55-519a-4e04-95a3-99b0f6e04b3e
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 97%

---

# データ収集について

Adobe Analytics 用にデータを収集する方法を説明します。

アドビでトラッキングする各ページには、アドビ認定の JavaScript コード（タグ）を埋め込みます。このコードを入手するには、担当のアカウントマネージャーにお問い合わせください。

大まかなデータ収集プロセスフローは次のようになります。

![](assets/data_collection.png)

1. 訪問者はデータ収集コードが含まれる Web ページを訪問します。
1. ページをロードすると、データ収集コードによってイメージリクエスト（Web ビーコンと呼ばれます）がアドビデータ収集サーバーに送信されます。イメージリクエストには、Web サイトでの訪問者のインタラクションを収集するためのデータが含まれます。
1. アドビではデータをレポートスイートに保存します。ログインしてレポートスイートデータにアクセスし、Web サイトでの訪問者のアクティビティに関するレポートを生成できます。

データの収集は非常に短時間で行われるので、ページロード時間に影響しません。ブラウザーの「**更新**」または「**戻る**」ボタンのクリックによるページビューも収集されます。ページがブラウザーキャッシュから取得された場合でも、JavaScript コードが実行されます。

デフォルトのホストグループを変更する方法については [Analytics でのデータ収集](/help/import/home.md)を参照してください。
