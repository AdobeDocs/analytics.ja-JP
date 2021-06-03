---
description: Adobe Mobile Services UI は、Adobe Analytics レポートスイートのモバイルアプリデータとプッシュ通知の送信機能を組み合わせて、アプリ内メッセージを生成します。
title: Mobile Services の VRS サポート
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
exl-id: 3082333a-514d-45c6-9432-da32bd27a2eb
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 96%

---

# Mobile Services の VRS サポート

Adobe Mobile Services UI は、Adobe Analytics レポートスイートのモバイルアプリデータとプッシュ通知の送信機能を組み合わせて、アプリ内メッセージを生成します。

## Mobile Services の VRS サポート {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

Adobe Mobile Services UI は、Adobe Analytics レポートスイートのモバイルアプリデータとプッシュ通知の送信機能を組み合わせて、アプリ内メッセージを生成します。

Adobe Mobile Services は、仮想レポートスイートをサポートします。ただし、複数のアプリを含む仮想レポートスイートを作成し、メッセージングアクティビティを実行する予定の場合、個別のアプリ ID をパラメーターとして指定する必要があります。プッシュメッセージを作成する場合、アプリ ID は、使用するセグメントのパラメーターの 1 つである必要があります。アプリ内メッセージを作成する場合、アプリ ID は、メッセージ用に確立する特性のパラメーターの 1 つである必要があります。これがおこなわれていない場合、メッセージは、セグメント／トリガー条件を満たすすべてのアプリのすべてのユーザーに送信／トリガーされます。

詳しくは、Adobe Mobile Services ドキュメントの[仮想レポートスイート](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/c-mob-vrs.html)を参照してください。
