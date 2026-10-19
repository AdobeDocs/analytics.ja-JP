---
title: モバイルライフサイクル指標
description: Mobile SDK を使用して収集されたデータに基づく指標です。
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: 'https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 10%
---
# モバイルライフサイクル指標

>[!BEGINSHADEBOX]

*このページは、Adobe Experience Platform Mobile SDKを通じて一般的に追跡されるデータを参照しています。 Mobile SDKを使用して追跡されたディメンションについては、[ モバイルライフサイクルディメンション ](../dimensions/lifecycle-dimensions.md)を参照してください。 ユーザーエージェントを使用するモバイルデバイス情報については、[ モバイル検索ディメンション ](../dimensions/mobile-dimensions.md)を参照してください。*

>[!ENDSHADEBOX]

| ライフサイクル指標名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| **[!UICONTROL 初回起動]** | アプリがインストールまたは再インストールされた後に初めて実行された回数。 | `a.InstallEvent` |
| **[!UICONTROL アップグレード]** | アップグレード後、またはバージョン番号が変更された後にアプリが初めて実行された回数。 | `a.UpgradeEvent` |
| **[!UICONTROL 起動回数]** | アプリが実行された回数（クラッシュ後やインストール後の実行を含む）。 また、ライフサイクルセッションのタイムアウトを超えた後にアプリがバックグラウンドから再開された場合も、起動がカウントされます。 | `a.LaunchEvent` |
| **[!UICONTROL クラッシュ]** | アプリが閉じられるまでにクラッシュした回数。 次にアプリを起動すると、クラッシュが報告されます。 | `a.CrashEvent` |
| **[!UICONTROL セッションの長さの合計]** | アプリが開かれていた時間とフォアグラウンドでの時間に基づいて、アプリセッションが続いた合計秒数。 各ローンチは、前のセッションの長さをレポートします。この指標は、これらの値の合計です。 | `a.PrevSessionLength` |
| **[!UICONTROL 合計アクション時間]** | セッション間のタイムアクションの開始から終了までの合計秒数（クロック時間）。 従来のMobile Services SDK （4.x）の`trackTimedAction` メソッドによって入力されました。 | `a.action.time.total` |
| **[!UICONTROL アプリでのアクション時間]** | セッション間の、タイムアクションの開始から終了までの間にアプリで費やした秒数。 従来のMobile Services SDK （4.x）の`trackTimedAction` メソッドによって入力されました。 | `a.action.time.inapp` |
| **[!UICONTROL ライフタイム値（イベント）]** | ユーザーの生涯価値（生涯購入、広告の閲覧、動画の完成、ソーシャルシェアなど）。 従来のMobile Services SDK （4.x）の`trackLifetimeValueIncrease` メソッドによって入力されました。 | `a.ltv.amount` |

>[!NOTE]
>
>[!UICONTROL Action Time Total]、[!UICONTROL Action Time In App]、および[!UICONTROL Lifetime Value （event） ]指標は、サポートされなくなった従来のMobile Services SDK （4.x）のメソッドによって入力されます。 Adobe Experience Platform Mobile SDKでは、これらの指標は自動入力されません。 時間制限付きアクションとライフタイムバリュートラッキングの代替案については、[Adobe Mobile Library （v4）からExperience Platform Analyticsへの移行](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/)を参照してください。
