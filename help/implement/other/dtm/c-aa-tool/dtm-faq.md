---
description: Adobe Analytics 導入の自動設定に関する FAQ です。自動設定の手法では、AppMeasurement コードを管理します。
keywords: Dynamic Tag Management;plug-ins;staging;effect on current settings;revision history;potential pitfalls;report suite id;currency code;tracking server;ssl tracking server;custom code;library management
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Adobe Analytics ツールに関する FAQ
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Adobe Analytics ツールに関する FAQ

Adobe Analytics 導入の自動設定に関する FAQ です。自動設定の手法では、[!DNL AppMeasurement] コードを管理します。

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> DTMを使用してAdobe Analyticsを実装する場合、プラグインを配置する場所を教えてください。 </p> </td> 
   <td colname="col2"> <p> If using DTM to manually host the <code> s_code</code>, plug-ins can be added in the same editor as the hosted <code> s_code</code>, just as it would be in a typical Adobe Analytics implementation. </p> <p>However, it is also an option to place the plug-ins in the editor within the <span class="term"> Customize Page Code</span> section of the tool settings. どちらの実装方法も効果は同じです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新しいバージョンのツールの設定を変更した場合、実稼動環境に発行する前にステージングでテストできますか。 </p> </td> 
   <td colname="col2"> <p>はい。 </p> <p>実稼動環境に展開する前に通常おこなうのと同じように、すべての変更をステージングでテストすることができます。ステージングで問題が見つかったので発行しない選択をした場合は、引き続き実稼動用コードが、新しい統合のリリース前と同様に機能します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>手動設定（既存ツールのデフォルト設定）から自動設定に切り替えると、現在の設定は影響を受けますか。 </p> </td> 
   <td colname="col2"> <p>いいえ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>手動のライブラリ管理から「アドビが管理」に切り替えると、現在の設定やコードは影響を受けますか。 </p> </td> 
   <td colname="col2"> <p>既に指定しているユーザーコードが基本 <span class="keyword">AppMeasurement</span> ライブラリによって上書きされます。このコードが引き続き実行されるように、コードをツール設定の最後にある新しい「<span class="wintitle">カスタムページコード</span>」セクションに移動する必要があります。この手法により、<span class="keyword">AppMeasurement</span> ライブラリをユーザーのカスタムコードとは別に管理（およびアップグレード）することができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新しい統合がリリースされても、<span class="keyword">Adobe Analytics</span> ツールの変更履歴は保持されますか。 </p> </td> 
   <td colname="col2"> <p>はい。 </p> </td> 
  </tr> 
 </tbody> 
</table>

「[Adobe Analytics ツールの追加](/help/implement/other/dtm/c-aa-tool/analytics-dtm.md)」を参照してください。

## 潜在的な問題 {#section_201BF9E0EB7D4BC2B72A617543C2030B}

現在 [!DNL Adobe Analytics] を使用している場合、わずかですが、統合によってデータ収集に関する問題が発生する可能性があります。これらの問題の発生が予想される状況としては、リリース後の実稼動環境にライブラリを発行する場合が考えられます（実稼動用コードは発行が発生するまでそのままの状態で保持されます）。

これらの問題を回避するには、次の確認をおこないます。

* ツールにレポートスイート ID が正しく入力されている。
* ツールのレポートスイート ID が [!DNL AppMeasurement] コードの ID と一致している。
* 通貨コード、文字セット、トラッキングサーバーおよび SSL トラッキングサーバーの設定フィールドに、サポートされている値が正しく設定されている。
* カスタムコードは、[!DNL Library Management] で定義されます。

