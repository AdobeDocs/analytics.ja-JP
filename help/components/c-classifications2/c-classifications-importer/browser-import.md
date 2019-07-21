---
description: ブラウザーを使用して分類データをインポート（アップロード）できます。この方法では、分類データのアップロードが単一のレポートスイートに制限されます。
seo-description: ブラウザーを使用して分類データをインポート（アップロード）できます。この方法では、分類データのアップロードが単一のレポートスイートに制限されます。
seo-title: ブラウザーインポート
solution: Analytics
subtopic: '分類      '
title: ブラウザーインポート
topic: 管理ツール
uuid: 56dfbf4c-36e6-49f4- b5cb-8ab714432825
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ブラウザーインポート

ブラウザーを使用して分類データをインポート（アップロード）できます。この方法では、分類データのアップロードが単一のレポートスイートに制限されます。

## Browser import {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

ブラウザーを使用して分類データをインポート（アップロード）できます。この方法では、分類データのアップロードが単一のレポートスイートに制限されます。

**[!UICONTROL 管理]** 者/ **[!UICONTROL 分類インポーター]**

## 分類ブラウザーインポート - フィールドの説明 {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> レポートスイートの選択 </td> 
   <td colname="col2"> <p>分類データをインポートするレポートスイート。インポートデータファイルが、このレポートスイートのデータセットの形式に一致する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分類するデータセット </td> 
   <td colname="col2"> <p>分類を受け取るデータセット。このドロップダウンリストには、分類用に設定されたレポートスイート内のすべてのレポートが含まれています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> インポートするファイルの選択 </td> 
   <td colname="col2"> <p>アップロードするインポートデータファイルを参照して指定します。 </p> <p>注意：アップロードできるファイルのサイズは最大で 1 MB です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 競合を無視してデータを上書きする </td> 
   <td colname="col2"> <p>インポートしたデータと競合する既存のデータを自動的に上書きします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> インポートの完了後、自動的に分類ファイルをダウンロードする </td> 
   <td colname="col2"> <p>新しくアップロードされた分類データを含むデータセットを表すタブ区切りファイル形式のファイルを自動的にダウンロードします。インポートによって一意の ID が作成された場合や、エラーが発生した場合、このファイルが自動的に生成されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## ブラウザーを使用した分類のインポート {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. **[!UICONTROL 管理者]** / **[!UICONTROL 分類インポーター]**&#x200B;をクリックします。
1. Click **[!UICONTROL Import File]**.
1. **[!UICONTROL ブラウザーインポート]** フィールドの設定を参照してください。
1. Click **[!UICONTROL Import File]**.
1. ステータスウィンドウで、処理メッセージを確認します。
1. (Conditional) If you selected **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specify where you want to store the resulting file when processing completes.
>インポートが正常に行われると、すぐにエクスポートで対応する変更が表示されます。ただし、Web ブラウザーでインポートした場合、レポートでのデータ変更には最大 4 時間かかります。FTP のインポートでは最大 24 時間かかります。

