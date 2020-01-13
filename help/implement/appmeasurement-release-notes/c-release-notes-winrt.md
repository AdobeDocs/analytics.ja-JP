---
description: 'null'
solution: Analytics,Experience Cloud
subtopic: Release notes
title: WinRT for Windows 8
topic: Developer and implementation
uuid: cec19d63-114c-4ef6-a55e-db6aad4e948b
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# WinRT for Windows 8{#winrt-for-windows}

>[!NOTE]
>
>ライブラリの現在のバージョンを検索するには、デバッグログを有効にしてください。

モバイルライブラリの[ダウンロード](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications)は[!DNL Developer Connection]で入手できます。

>[!NOTE]
>
>[!DNL Windows] 版 [!DNL WinRT] 8 SDK は [Windows 8.1 ユニバーサルアプリストア](../appmeasurement-release-notes/c-release-notes-winu.md) SDK により置き換えられます。今後、この SDK の開発はおこなわれません。

## バージョン 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

リリース日：**2014 年 6 月 18 日**

位置情報、ライフタイム値、時間指定アクション、オプトインサポートなどの新機能を備えた新しいバージョンです。

## バージョン 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

リリース日：**2014 年 5 月 23 日**

バグが修正され、パフォーマンスが改善されました。

## バージョン 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

リリース日：**2013 年 10 月 18 日**

* [!DNL Windows] 8.1 互換

## バージョン 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

リリース日：**2013 年 4 月 19 日**

* 以前のセッションの長さが誤って計算されることがある問題を修正しました。

## バージョン 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

リリース日：**2013 年 3 月 22 日**

* `ADMS_Measurement.visitorID` にデフォルト値があらかじめ設定されるようになりました。
* デバイス情報の取得に関する問題を修正しました。

## バージョン 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

リリース日：**2013 年 2 月 22 日**

* 非推奨だった `offlineThrottleDelay` の設定は、スレッドの最適化によって不要になりました。この設定は後方互換性のために引き続き保持されますが、効果は何もありません。
* `DayOfWeek` が他のプラットフォームで収集される値と同じ 1-base の日曜始まりになりました。
* ライフサイクル追跡を効率化するために、TrackingHelper.js でのイベントリスナーの自動登録機能を追加しました。

## バージョン 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

リリース日：**2012 年 11 月**

* 画面解像度が C#、C++ および HTML5／WinJS プラットフォーム用に正確に収集されるようになりました。
* 現在、`ADMS_Churn` クラスは内部用です。アプリケーションのライフサイクルトラッキングのベストプラクティスを利用するには、以下の呼び出しを使用します。

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* `public double maxSessionLength` 変数が `ADMS_Measurement` に追加され、以前のユーザーセッションの最大セッション長を設定できるようになりました。登録されているセッション長がこの最大値を超えると、最大セッション長が送信されます。デフォルトの `maxSessionLength` は 3600（秒）です。
* `lifecycleSessionTimeout` 設定変数を追加しました。この変数によって、アプリケーションを再起動する際に、新しいセッションが認識されるのに必要な経過時間を秒単位で指定できます。
* ライフサイクル指標に「以前のセッションの長さ」という新しい指標を追加しました。
* TrackingHelper を更新して明確化しました。
* メディアモジュールのバグを修正しました。

## バージョン 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**2012 年 10 月**

初回リリース。
