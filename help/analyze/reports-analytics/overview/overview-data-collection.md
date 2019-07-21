---
description: Adobe Analytics 用にデータを収集する方法を説明します。
seo-description: Adobe Analytics 用にデータを収集する方法を説明します。
seo-title: データ収集について
solution: Analytics
subtopic: はじめに
title: データ収集について
topic: Reports and Analytics
uuid: 4dd9a23d- ad49-4841-8f4c-32c3993851f2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# データ収集について{#about-data-collection}

Adobe Analytics 用にデータを収集する方法を説明します。

アドビでトラッキングする各ページには、アドビ認定の JavaScript コード（タグ）を埋め込みます。このコードを入手するには、担当のアカウントマネージャーにお問い合わせください。

大まかなデータ収集プロセスフローは次のようになります。

![](assets/data_collection.png)

1. 訪問者はデータ収集コードが含まれる Web ページを訪問します。
1. ページをロードすると、データ収集コードによってイメージリクエスト（Web ビーコンと呼ばれます）がアドビデータ収集サーバーに送信されます。イメージリクエストには、Web サイトでの訪問者のインタラクションを収集するためのデータが含まれます。
1. アドビではデータをレポートスイートに保存します。ログインしてレポートスイートデータにアクセスし、Web サイトでの訪問者のアクティビティに関するレポートを生成できます。

データの収集は非常に短時間で行われるので、ページロード時間に影響しません。ブラウザーの「**更新**」または「**戻る**」ボタンのクリックによるページビューも収集されます。ページがブラウザーキャッシュから取得された場合でも、JavaScript コードが実行されます。

See [Data Collection in Analytics](https://marketing.adobe.com/resources/help/en_US/reference/usecase_sending_data_to_sc.html).
