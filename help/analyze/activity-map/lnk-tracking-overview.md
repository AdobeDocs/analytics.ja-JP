---
description: 'Activity Map では、より強力なアルゴリズムを使用してリンクを追跡します。 '
title: 強力なリンクトラッキング
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 98%

---


# 強力なリンクトラッキング

Activity Map では、より強力なアルゴリズムを使用してリンクを追跡します。

* ページ領域の追跡を含めることにより、ページ上の複数の位置にリンクが表示されるために同じリンクが複数の異なるデバイスにまたがって混同される問題を回避します。
* リンクの一意性を保証します。つまり、リンク ID の問題や異なるブラウザーをまたがることから生じる問題により、個々のリンクが別のものと間違われることがなくなります。

Activity Map のリンクトラッキングについて詳しくは、[ここ](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)を参照してください。

## Activity Map リンクトラッキングにより PII データが収集される可能性について {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION]
>
>Activity Map トラッキングをオンにすると、個人を特定できる情報（PII）のデータを収集できます。このデータは、そのまま使用するか、その他の情報と共に使用して、個人を特定および検索したり、個人と連絡を取ったり、コンテキスト内で個人を特定したりすることができます。

Activity Map トラッキングによって PII データが収集される可能性がある既知のケースには次のようなものがあります。

* `Mailto` リンク。mailto リンクは、メールを送信するためにコンピューター上のデフォルトのメールクライアントを起動するの HTML リンクです。
* `User ID` リンク。ユーザーがログインすると、Web サイトのヘッダー／フッターに表示される場合があります。
* 金融機関では、口座番号がリンクとして表示されている場合があります。そのリンクをクリックすると、リンクのテキストが収集されます。
* また、医療関連の Web サイトでも、PII データがリンクとして表示されている場合があります。これらのリンクをクリックすると、リンクのテキストが収集されるので、PII データが収集されることになります。
