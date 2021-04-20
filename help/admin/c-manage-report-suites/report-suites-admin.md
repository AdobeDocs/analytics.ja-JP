---
description: レポートスイートでは、選択した Web サイト、Web サイト群、または Web ページのサブセットに関する完全な独立レポートが定義されます。通常、レポートスイートは 1 つの Web サイトですが、複数サイトの数値を組み合わせて合計を示すグローバルセグメントとなる場合もあります。Adobe Analytics ソリューションにログインしたら、使用するレポートスイートを 1 つ選択します（レポートスイートを組み合わせたロールアップを使用する場合を除く）。また、サイトの一部に対してレポートを実行する場合は、レポートスイートが Web サイトより小さくなることがあります。Analytics ソリューションが集約され、これらのデータストアについてレポートします。管理ツールの Report Suite Manager では、レポートスイートでのデータの処理方法を制御するルールを定義できます。
title: レポートスイートマネージャー
feature: Admin Tools
uuid: 018c4f63-4d87-4a2e-8c71-1ba7f5dd9446
exl-id: c36e5378-c8a7-4f18-b143-8ce862638c76
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 100%

---

# レポートスイートマネージャー

レポートスイートでは、選択した Web サイト、Web サイト群、または Web ページのサブセットに関する完全な独立レポートが定義されます。通常、レポートスイートは 1 つの Web サイトですが、複数サイトの数値を組み合わせて合計を示すグローバルセグメントとなる場合もあります。Adobe Analytics ソリューションにログインしたら、使用するレポートスイートを 1 つ選択します（レポートスイートを組み合わせたロールアップを使用する場合を除く）。また、サイトの一部に対してレポートを実行する場合は、レポートスイートが Web サイトより小さくなることがあります。Analytics ソリューションが集約され、これらのデータストアについてレポートします。管理ツールの Report Suite Manager では、レポートスイートでのデータの処理方法を制御するルールを定義できます。

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**

>[!NOTE]
>
>仮想レポートスイートは、**[!UICONTROL Analytics]**／**[!UICONTROL コンポーネント]**／**[!UICONTROL 仮想レポートスイート]**&#x200B;で管理されます。[仮想レポートスイートのドキュメント](/help/components/vrs/vrs-about.md)を参照してください。

## Report Suite Manager の説明 {#section_0C94DC9EACDA4F5891F5CD63EE80B125}

以下の表では、[!UICONTROL Report Suite Manager] ページのエレメントについて説明しています。

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> レポートスイートの選択</span> </td> 
   <td colname="col2"> <p><span class="wintitle">Report Suite Manager</span> では、選択したレポートスイートが強調表示されます。複数のレポートスイートを選択するには、<span class="uicontrol">Ctrl</span> キーまたは <span class="uicontrol">Shift</span> キーを押しながらクリックします。 </p> <p>選択したレポートスイートは、別のレポートスイートを選択するまで選択されています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> ダウンロード</span> </td> 
   <td colname="col2"> 現在選択されているレポートスイートに関するすべての設定が含まれる Excel スプレッドシートを生成します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">検索</span> </td> 
   <td colname="col2"> レポートスイートリスト内にある特定のレポートスイートを見付けることができます。検索ツールには、基本的な名前ベースの検索と、より詳細な検索を行うためのアドバンス検索ページがあります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">グループ </span> </td> 
   <td colname="col2"> <p> レポートスイートをカスタムグループにまとめて整理できます。類似した設定を共有するレポートスイートや、よく一緒に編集する複数のレポートスイートに一括してすばやくアクセスできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 保存済みの検索結果</span> </td> 
   <td colname="col2"> <p>メンバーを判断する条件のセットを定義するために<span class="wintitle">アドバンス検索</span>機能を使用する動的グループ。<span class="wintitle">Report Suite Manager</span> でレポートスイートを追加または変更する際、<span class="wintitle">保存済みの検索結果</span>により、条件に一致するレポートスイートが自動的に追加されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> ロールアップ</span> </td> 
   <td colname="col2"> <p>ロールアップとは、他の複数のレポートスイートのトラッキングデータを組み合わせる単一のレポートスイートのことです。 </p> <p>詳しくは、<a href="/help/admin/c-manage-report-suites/rollup-report-suite.md">ロールアップレポートスイート</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 設定の編集</span> </td> 
   <td colname="col2"> レポートスイートを編集すると、選択したすべてのレポートスイートに編集内容が適用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 新規作成</span> </td> 
   <td colname="col2"><a href="/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md">新しいレポートスイート</a>を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> コラムのカスタマイズ</span> </td> 
   <td colname="col2"><span class="wintitle">Report Suite Manager</span> に追加するコラムを選択できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">レポートスイート ID</span> </td> 
   <td colname="col2"><a href="/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md">新しいレポートスイート</a>を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> サイトのタイトル</span> </td> 
   <td colname="col2"> <p>管理ツール、およびマーケティングレポートヘッダーのレポートスイートドロップダウンリストで、レポートスイートを識別します。 </p> <p><a href="/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md">新しいレポートスイート</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> ベース URL</span> </td> 
   <td colname="col2"> <p>レポートスイートのベースドメインを定義します。 </p> <p><a href="/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md">新しいレポートスイート</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>
