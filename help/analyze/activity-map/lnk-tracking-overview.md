---
description: '[!DNL Activity Map]は、 '
seo-description: '[!DNL Activity Map]は、 '
seo-title: 強力なリンク追跡
solution: Analytics
title: 強力なリンク追跡
topic: Activity Map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# 強力なリンク追跡

[!DNL Activity Map] より堅牢なアルゴリズムを使用して、リンクを追跡します。

* ページ領域の追跡を含めることにより、ページ上の複数の位置にリンクが表示されるために同じリンクが複数の異なるデバイスにまたがって混同される問題を回避します。
* リンクの一意性を保証します。つまり、リンク ID の問題や異なるブラウザーをまたがることから生じる問題により、個々のリンクが別のものと間違われることがなくなります。

For more on link tracking in [!DNL Activity Map], go [here](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## How [!DNL Activity Map] link tracking may collect PII Data {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION] 追跡機能をオンにす [!DNL Activity Map] ると、個人情報(PII)データを収集している可能性があります。 そのようなデータは単独で、または他の情報を組み合わせることによって、個人の識別、個人への連絡、または個人の所在地の特定に利用できたり、文脈から個人を識別するために利用できたりします。

Here are some known cases where PII data might be collected using [!DNL Activity Map] Tracking:

* `Mailto` リンク、 mailto リンクは、メールを送信するためにコンピューター上のデフォルトのメールクライアントを起動するの HTML リンクです。
* `User ID` ユーザーがログインした後にWebサイトのヘッダー/フッターに表示される可能性のあるリンク。
* 金融機関では、口座番号がリンクとして表示されている場合があります。そのリンクをクリックすると、リンクのテキストが収集されます。
* また、医療関連の Web サイトでも、PII データがリンクとして表示されている場合があります。これらのリンクをクリックすると、リンクのテキストが収集されるので、PII データが収集されることになります。
