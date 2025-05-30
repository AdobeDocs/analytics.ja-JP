---
description: 仮想レポートスイートの作成を始める前に、以下に注意してください。
keywords: 仮想レポートスイート
title: 仮想レポートスイートの作成
feature: VRS
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 62%

---

# 仮想レポートスイートの作成

仮想レポートスイートの作成を始める前に、以下に注意してください。

* 管理者以外のユーザーは、仮想レポートスイートマネージャーを表示できません。
* 仮想レポートスイートは共有できません。「共有」するには、グループや権限を使用します。
* 仮想レポートスイートマネージャーには、独自の仮想レポートスイートのみが表示されます。 他のユーザーの仮想レポートスイートを表示するには、「すべて表示」をクリックする必要があります。

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL 仮想レポートスイート]** に移動します。
1. 「**[!UICONTROL 追加 +]**」をクリックします。

   ![](assets/new_vrs.png)

## 設定の定義

「[!UICONTROL 設定]」タブでこれらの設定を定義し、「**[!UICONTROL 続行]**」をクリックします。

| 要素 | 説明 |
| --- |--- |
| 名前 | 仮想レポートスイートの名前は親レポートスイートから継承されません。別の名前を指定する必要があります。 |
| 説明 | ビジネスユーザーにとってわかりやすい説明を追加します。 |
| タグ | タグを追加してレポートスイートを整理できます。 |
| ソース | レポートスイートはこの仮想レポートスイートから次の設定を継承します。ほとんどのサービスレベルと機能（eVar 設定、処理ルール、分類など）を継承します。仮想レポートスイートの継承設定を変更するには、親レポートスイートを編集する必要があります（管理者/レポートスイート）。 |
| タイムゾーン | タイムゾーンの選択はオプションです。選択したタイムゾーンは、仮想レポートスイートと共に保存されます。 タイムゾーンを選択していない場合は、親レポートスイートのタイムゾーンが使用されます。仮想レポートスイートを編集すると、仮想レポートスイートと共に保存されたタイムゾーンがドロップダウンセレクターに表示されます。 タイムゾーンサポートが追加される前に仮想レポートスイートが作成された場合、ドロップダウンセレクターに親レポートスイートのタイムゾーンが表示されます。 |
| セグメント | セグメントは、1 つだけ追加することも、積み重ねることもできます。メモ：2 つのセグメントを積み重ねると、それらのセグメントが AND ステートメントで結合されます。これを OR ステートメントに変更することはできません。仮想レポートスイートで現在使用中のセグメントを削除または編集しようとすると、警告が表示されます。 |

## 訪問の定義

「[!UICONTROL 訪問の定義]」タブでこれらの設定を定義し、「**[!UICONTROL 続行]**」をクリックします。

![](assets/visit-definition.png)


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ 訪問定義の調整 ](https://video.tv.adobe.com/v/3428475?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]

| 要素 | 説明 |
| --- |--- |
| **訪問定義を設定** |  |
| レポート時間処理を有効にする | レポート時間処理を使用して、デフォルトの訪問のタイムアウトまでの長さを変更します。これらの設定は、非破壊的で、Analysis Workspace でのみ適用します。[詳細情報](/help/components/vrs/vrs-report-time-processing.md) |
| 訪問タイムアウト | 各ユニーク訪問者がどのくらいの時間非アクティブであった場合に新しい訪問を自動的に開始するかを定義します。これは、訪問回数指標、訪問セグメントコンテナおよび訪問の期限が切れた eVar に影響します。 |
| イベントで新しい訪問を開始 | セッションがタイムアウトしているかどうかに関係なく、指定したイベントが発生したら、新しいセッションが開始されます。 |
| **モバイルアプリ訪問設定** | Adobeの Mobile SDK で収集されるモバイルアプリのヒット数について、訪問回数をどのように定義するかを変更します。 これらの設定は非破壊的で、Analysis Workspaceでのみ適用します。 |
| バックグラウンドヒットで新しい訪問が開始されないようにする | バックグラウンドヒットで、新しい訪問が開始されないようにしたり、訪問回数およびユニーク訪問者指標が水増しされないようにします。 |
| 各アプリの起動時に新しい訪問を開始 | アプリの起動が発生したら新しいセッションを開始します。[詳細情報](/help/components/vrs/vrs-mobile-visit-processing.md) |

## コンポーネントの追加と名前変更

![](assets/components.png)

1. 「[!UICONTROL コンポーネント]」タブで、Analysis Workspace のこの仮想レポートスイート用のキュレーションを適用するチェックボックスをオンにします。
仮想レポートスイートのキュレーションについて詳しくは、「[ 仮想レポートスイートコンポーネントのキュレーション ](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-components.html?lang=ja#virtual-report-suites)」を参照してください。

1. 仮想レポートスイートに含めるコンポーネント（ディメンション、指標、セグメント、または日付範囲）を [!UICONTROL &#x200B; 含まれるコンポーネント &#x200B;] セクションにドラッグします。

1. 完了したら、「**[!UICONTROL 保存]**」をクリックします。

## データのプレビュー

各タブの右側で、元のレポートスイートと比較した、この仮想レポートスイートでの合計ヒット数、合計訪問回数、合計訪問者数をプレビューできます。

## 製品の互換性の表示

仮想レポートスイートの一部の機能は、すべてのAdobe Analytics製品でサポートされているわけではありません。 製品互換性リストを使用すると、現在の仮想レポートスイートの設定に基づいて、Adobe Analytics内でサポートされている製品を確認できます。
