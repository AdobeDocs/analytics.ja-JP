---
description: Analysis Workspace でアラートを使用します。
title: アラートビルダーの概要
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 97%

---

# アラートビルダー

>[!IMPORTANT]
>
>インテリジェントアラートは、Adobe [!DNL Analytics] Prime および Adobe [!DNL Analytics] Ultimate のお客様のみご利用いただけます。

次の 3 つの方法のいずれかで、アラートビルダーにアクセスします。

* Analysis Workspace で以下のショートカットを使用する。

  `ctrl (or cmd) + shift + a`
* **[!UICONTROL Workspace]**／**[!UICONTROL コンポーネント]**／**[!UICONTROL 新しいアラート]**&#x200B;に移動する。
* 1 つまたは複数のフリーフォームテーブル行項目を選択し、右クリックして、「**[!UICONTROL 選択からアラートを作成]**」を選択する。

アラートビルダーインターフェイスは、[!DNL Analytics] でセグメントや計算指標を作成していたユーザーにとってなじみのあるものです。

![](assets/alert_builder.png)

**アラート名**

アラート名を指定します。アラート名には、レポート名または指標のしきい値を含めることができます。

**時間の精度**

いつ指標がチェックされるかを、1 時間ごと、毎日、毎週または毎月から指定します。

>[!NOTE]
>
>カスタムカレンダーを含むレポートスイートの場合、アラートビルダーの月単位の精度をサポートしません。

**受信者**

アラートの送信先を指定します。アラートは、[!DNL Analytics] ユーザー、[!DNL Analytics] グループ、生の電子メールアドレスまたは電話番号に送信できます。

>[!IMPORTANT]
>
>電話番号には、先頭に「+」と[国番号](https://countrycode.org/)を付ける必要があります。

**有効期限**

アラートの有効期限を設定します。

**次の場合にアラートを送信...**

*... いずれかの指標によるトリガー*

* トリガーを追加するキャンバスに指標をドラッグ＆ドロップします。

  注意：現在選択されているレポートスイートと互換性がないコンポーネント（指標、ディメンション、セグメント）がアラートに含まれている場合は、「**互換性のないコンポーネント**」というメッセージが表示されます。

* アラートが設定される前に指標が超過している必要があるしきい値を指定します。この値をしきい値に設定し、以下のいずれかの条件にすることができます。

   * 異常値が存在する
   * 異常値が予測より上
   * 異常値が予測より下
   * 異常値超過
   * 以上
   * 以下
   * 変更（％）

* 異常値超過は、既存の（静的な）しきい値を超える新しい条件です。トリガーを動的に定義する異常値検出アルゴリズムをプルします。90％、95％、99％、99.75％、99.9％ のしきい値を設定できます。
* 毎時の精度は 99.75％、毎日の精度は 99％ のしきい値で設定されます。
* 計算指標も使用できることに注意してください。

*... これらすべてのフィルターを使用*

セグメントまたはディメンションをここにドラッグ＆ドロップしてフィルターを追加します。例えば、「モバイルデバイスのみ」セグメントの追加は、ルールがモバイルデバイスに対してのみトリガーするということを意味します。

追加のフィルターは、AND ステートメントを使用して追加されます。

**ルールを追加**

ギアアイコンをクリックして、AND または OR ルールを追加できます。

## アラートプレビュー {#section_10D75BA7B77E4C5FAF58A719C082E070}

インタラクティブアラートプレビューは、過去の経験に基づいて、アラートが実行されるおよその頻度を表示します。

例えば、時間の精度を毎日に設定すると、プレビューにより、最近の 30 または 31 日間で、特定の指標に対してアラートが何回トリガーされたかがわかります。

トリガーされているアラートが多すぎる場合は、[アラートマネージャー](/help/components/c-alerts/alert-manager.md)でしきい値を調整できます。

![](assets/alert_preview.png)
