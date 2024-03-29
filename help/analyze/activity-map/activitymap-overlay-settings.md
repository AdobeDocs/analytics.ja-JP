---
description: Activity Map 設定パネルを使用すると、すべてのタイプのオーバーレイビジュアライゼーションの設定およびプロパティを変更できます。
title: Activity Map の設定
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 50%

---

# Activity Map の設定

Activity Map 設定パネルを使用すると、すべてのタイプのオーバーレイビジュアライゼーションの設定およびプロパティを変更できます。

Activity Map Settings パネルにアクセスするには、Activity Map ツールバーの歯車アイコンをクリックします。

## 一般設定 {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL 会社]** | 該当するログイン会社を選択します。 |
| **[!UICONTROL レポートスイート]** | アクセス可能なレポートスイートリストはウェブページタグで定義されるレポートスイートに制限されなくなりました。選択したレポートスイート（ページ上のタグのいずれかに対応）を別のレポートスイートで置き換えることができるようになりました。この新しいレポートスイートは、ページ上のタグにリンクされる必要はありません。Activity Map設定で選択されているレポートスイートを変更した場合、保存処理を実行すると、影響を受ける Analytics レポートがすべて更新されます。<br>**重要**: [!UICONTROL 仮想レポートスイート] 次と互換性がありません： [!UICONTROL ライブモード]を使用し、 [!UICONTROL 標準モード]. 次の場所にいる場合： [!UICONTROL ライブモード] 標準レポートスイートの場合は、 [!UICONTROL 仮想レポートスイート] このダイアログでは、 **[!UICONTROL OK]** ここに、標準モードが表示されます。 また、レポートスイートのカレンダータイプ（グレゴリオ暦、小売、カスタムなど）に一致するように、カレンダーコントロールが再初期化されます。 |
| **[!UICONTROL ページ名]** | これらの設定を適用するページです。 |
| **[!UICONTROL 言語]** | この選択は、Adobe Analytics に提供される言語に対応します。 |
| **[!UICONTROL ラベルのオーバーレイ]** | <ul><li>**[!UICONTROL ラベルなし]**：グラデーションオーバーレイのみに該当します。この場合、オーバーレイの色は、リンクのランク付けの意味を表します</li><li>**[!UICONTROL 値]**：そのリンクの生の指標合計。</li><li>**[!UICONTROL 割合]**：ページの合計指標に対するこのリンクの指標の割合。</li><li>**[!UICONTROL ランク]**：レンダリングされたページに存在するすべてのリンクの中でのこのリンクのランク。</li></ul> |
| **[!UICONTROL ラベルのフォントサイズ]** | スライダーを使用して、オーバーレイラベルのフォントサイズを読みやすいように拡大、縮小できます。 |
| **[!UICONTROL グラデーション/バブルの色]** | グラデーションまたはバブルのオーバーレイビジュアライゼーションにオーバーレイリンクランクを表示するには、様々な色から選択します。 |
| **[!UICONTROL カラーグラデーションの基準]** | <ul><li>**[!UICONTROL 上位 30 位のランキング]**：色の強度が上位 30 件の値に対して標準化されます。</li><li>**[!UICONTROL 指標絶対値]**：色の強度は指標絶対値の関数です。</li></ul> |
| **[!UICONTROL グラデーションの透明度]** | グラデーションオーバーレイの透明度のレベルを選択します。この設定は、 [!UICONTROL バブル] オーバーレイ。 |

## 標準設定 {#section_24DB95376E1A448494ECF3F57743FC19}

これらの設定は、標準モードのオーバーレイに適用されます。

![](assets/settings_standard.png)

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL 動的データのフィルタリング]** | このドロップダウンリストでは、<ul><li>（デフォルト）ページ上のすべてのリンク</li><li>ページ上のランク付けされたリンクの上位（上位）または下位（下位）の数。#は 1、10、50、100 の選択肢です。</li></ul> |
| **[!UICONTROL ヒットのなかったリンクのオーバーレイを非表示にします]**. | データのないリンクのオーバーレイの表示/非表示を切り替えるチェックボックス。<ul><li>（デフォルト）このチェックボックスがオンの場合、リンクに ActivityMap リンクデータがない場合、オーバーレイは表示されません。</li><li>このチェックボックスがオフの場合、リンクに ActivityMap リンクデータがない場合、オーバーレイが表示され、ラベルが「 — 」になります。これは、該当なし（該当なし）を意味します。 |

## ライブ設定 {#section_D30F6E62FB5D404090B588F396A460AF}

これらの設定は、ライブモードのオーバーレイに適用されます。

![](assets/settings_live.png)

| 設定 | 説明 |
|---|---|
| **[!UICONTROL 上位を表示]** | 次の手順で **[!UICONTROL 勝者]** または **[!UICONTROL 敗者]** （または両方）をオーバーレイとして、リンク数を選択します。 |
| **[!UICONTROL 下位を除外（％）]** | データの少ない勝者と敗者のリンクを排除します。下位のほうから指定した割合のリンク変更をフィルターで除外して、意味のある増減を示すデータが十分に含まれているリンクのみを表示します。割合は、ページ上のリンク数に基づいて計算されます。例えば、200 個のリンクのリストの下部 10%を除外すると、下部 20 個のリンクが除外されます。 |
| **[!UICONTROL データを自動更新]** | 新しい期間を計算する際に、インターフェイスに表示される Analytics データを自動的に更新するかどうかを指定できます。 |
| **[!UICONTROL 自動更新期間]** | チェックすると、新しいデータを取得するたびに Web ページが更新され、ページ上のリンクを収集されたデータとより密接に同期できます。 |
