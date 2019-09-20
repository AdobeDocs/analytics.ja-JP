---
description: 統合をアクティブ化するには、Data Connectorsインターフェイス内の設定ウィザードを完了する必要があります。
seo-description: 統合をアクティブ化するには、Data Connectorsインターフェイス内の設定ウィザードを完了する必要があります。
seo-title: Adobe統合ウィザードの完了
title: Adobe統合ウィザードの完了
uuid: 75260b92-a6f5-44b6-b3ea-d5945fdd1ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Adobe統合ウィザードの完了{#completing-the-adobe-integration-wizard}

統合をアクティブ化するには、Data Connectorsインターフェイス内の設定ウィザードを完了する必要があります。

1. Adobe Experience cloud内のData Connectors（旧称Genesis）領域に移動します。
1. Demandbase 2.0統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次の項目を設定します。

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 電子メールアドレス </td> 
   <td colname="col2"> 主連絡先の電子メールアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 説明 </td> 
   <td colname="col2"> （オプション）この統合設定の説明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase APIキー </td> 
   <td colname="col2"> これは、Demandbaseの担当者から入手できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> カスタムDemandbaseディメンション#N </td> 
   <td colname="col2"> これらは、8つのオプションディメンションのIDです。 詳細は、「Demandbaseカスタムディメンション」を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adobe targetに送信 </td> 
   <td colname="col2">「true」の場合、Demandbaseディメンションは、非表示のmboxを使用してAdobe targetにも送信されます。 <p>注意： ディメンションを収集するには、設定済みのmbox.jsファイルをWebページに実装する必要があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 次の「変数マッピング」項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | Demandbaseディメンション | 使用可能なeVar変数をレポートスイートから選択します。 |
   | Demandbaseカスタムディメンション（オプション） | 使用可能なeVar変数をレポートスイートから選択します。 |

1. カスタムディメンションの名前を設定します（該当する場合）。

   1. 手順4でカスタムディメンションを含め、手順5でオプションのeVarをマッピングした場合は、これらのディメンションにわかりやすい名前を付ける必要があります。 例えば、「stock_ticker」をカスタムディメンション1として入力する場合は、「ディメンション1」を含むボックスを「Stock Ticker」に変更する必要があります。
   1. 標 **準** 8のディメンションの名前（Demandbase SID、会社名、業種など）は変更しないでください。

1. Demandbase統合ダッシュボードを自動的に作成する場合は、このチェックボックスをオンにします（推奨）。
1. すべての設定項目を確認し、「今すぐアクティブ化」 **[!UICONTROL をクリックしま]**&#x200B;す。

