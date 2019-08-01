---
description: 統合をアクティブ化するには、Data Connectorsインターフェイス内で設定ウィザードを完了する必要があります。
seo-description: 統合をアクティブ化するには、Data Connectorsインターフェイス内で設定ウィザードを完了する必要があります。
seo-title: Adobe統合ウィザードの完了
title: Adobe統合ウィザードの完了
uuid: 75260b92- a6f5-44b6- b3ea- d5945fdd1ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

統合をアクティブ化するには、Data Connectorsインターフェイス内で設定ウィザードを完了する必要があります。

1. Adobe Marketing Cloud内のData Connectors（以前のGenesis）領域に移動します。
1. Demandbase2.0統合ウィザードを起動します。
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
   <td colname="col2"> プライマリ連絡先の電子メールアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 説明 </td> 
   <td colname="col2"> （オプション）この統合設定の説明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase APIキー </td> 
   <td colname="col2"> これは、Demandbase担当者から入手できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> カスタムDemandbaseディメンション# N </td> 
   <td colname="col2"> これらは8つのオプションディメンションのIDです。詳しくは、Demandbase Custom Dimensionsを参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adobe Targetに送信 </td> 
   <td colname="col2">"true"の場合、非表示mboxを使用してDemandbaseディメンションもAdobe Targetに送信されます。 <p>注意:収集されるディメンションについては、設定済みのmbox. jsファイルをWebページに実装する必要があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 次の変数マッピング項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | Demandbase Dimensions | 利用可能なeVar変数をレポートスイートから選択します。 |
   | Demandbaseカスタムディメンション（オプション） | 利用可能なeVar変数をレポートスイートから選択します。 |

1. カスタムディメンションの名前を設定します（該当する場合）。

   1. 手順4でカスタムディメンションを含めるように選択し、手順5でオプションのeVarをマッピングする場合は、それらのディメンションにわかりやすい名前を付ける必要があります。例えば、"stock_ ticker"をカスタムディメンション1として入力する場合は、"Dimension1"を含むボックスを"Stock Ticker"に変更します。
   1. **標準8次元の名前** （DemandbaseのSID、会社名、業界など）は変更しないでください。

1. このチェックボックスをオンにすると、Demandbase Integrationダッシュボードが自動的に作成されます（推奨）。
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

