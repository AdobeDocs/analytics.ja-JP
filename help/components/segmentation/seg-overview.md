---
description: セグメントを使用すると、特性や web サイトでのやり取りに基づいて訪問者のサブセットを識別できます。セグメントは、分類された閲覧者インサイトとして設計され、特定のニーズに合わせて作成することができ、確認、編集および他のチームメンバーと共有したり、他の Adobe 製品や Analytics 機能で使用したりできます。
title: セグメントについて
feature: Segmentation
exl-id: 11d930ca-5d59-4ea5-b6e5-fe3d57be94fd
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 78%

---

# セグメントについて

セグメントを使用すると、特性や web サイトでのやり取りに基づいて訪問者のサブセットを識別できます。セグメントは、特定のニーズに合わせて構築し、検証、編集、他のチームメンバーと共有、他のアドビ製品や Analytics 機能で使用したりできるオーディエンスインサイトとして設計されています。

セグメントは、[!UICONTROL 訪問者]、[!UICONTROL 訪問]および[!UICONTROL ヒット]の各レベル階層に基づき、ネストされたコンテナモデルを使用します。ネストされたコンテナを使用することで、コンテナ間およびコンテナ内のルールに基づいて、訪問者の属性とアクションを定義できます。Analytics セグメントは、[!DNL Adobe Experience Cloud] の複数の製品および機能間で構築、承認、共有、保存および実行できます。セグメントはレポートから生成したり、ダッシュボードレポートに組み込んだりできます。また、セグメントをブックマークに登録すると、セグメントにすばやくアクセスできるようになります。

セグメントビルダーでセグメントを作成および保存したり、（[!UICONTROL Analysis Workspace] の）フォールアウトレポートからセグメントを生成したりできます。 また、事前作成されたセグメントをネストされたコンテナ間の特定のルールに基づいて利用および拡張し、結果をフィルタリングしてレポートに適用することもできます。また、複数のセグメントをまとめて、[積み重ねセグメント](/help/components/segmentation/segmentation-workflow/seg-workflow.md)として使用することもできます。

セグメントは次の項目を識別します。

- 訪問者（国、性別、コーヒーショップ）
- 訪問者が使用するデバイスやサービス（ブラウザー、検索エンジン、モバイルデバイス）
- 訪問者がどこからアクセスしてきたか（検索エンジン、前の出口ページ、自然検索）
- 他にもたくさんあります。

<!--![](assets/seg.png)-->

セグメントは、次の値に基づくことができます。

- 属性に基づく訪問者 - ブラウザーのタイプ、デバイス、訪問回数、国、性別。
- インタラクションに基づく訪問者 - キャンペーン、キーワード検索、検索エンジン。
- 出口および入口に基づく訪問者 - Facebook、定義済みのランディングページ、参照ドメインからの訪問者。
- カスタム変数に基づく訪問者 - フォームフィールド、定義済みのカテゴリ、顧客 ID。

セグメントビルダーでオーディエンスセグメントを作成する場合は、コンテナ間の [!UICONTROL AND] および [!UICONTROL OR] 演算子を使用して条件を定義します。

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 訪問者</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">AND</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>
</table>

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 訪問者</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">OR</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>
</table>

<!--![](assets/standard_segment_containers.png)-->

このタイプのセグメントは、[!UICONTROL AND] および [!UICONTROL OR] 演算子を使用して結合された特性に基づいてデータセットをフィルタリングします。

- [レポートやプロジェクトに複数のセグメントを適用](/help/components/segmentation/segmentation-workflow/t-seg-apply.md)できます。
- セグメントが、レポートスイート全体で共通になりました。
- [ セグメントビルダー ](/help/components/segmentation/segmentation-workflow/seg-build.md) を使用すると、セグメントを簡単に作成できます。
- [ セグメントマネージャー ](/help/components/segmentation/segmentation-workflow/seg-manage.md) を使用すると、セグメントの共有、タグ付け、検証、承認などの機能を備えた [ ワークフロー ](/help/components/segmentation/segmentation-workflow/seg-workflow.md) を設定できます。
- フォルダーを使用する代わりに[セグメントにタグを設定](/help/components/segmentation/segmentation-workflow/seg-tag.md)して、セグメントを整理したり検索したりできます。
- [ 順次セグメント ](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md) を作成できます。
- [!UICONTROL ページビュー]コンテナは、ページビューだけにとどまらずあらゆる種類のデータをセグメント化するコンテナであることを示すために、名称が[!UICONTROL ヒット]コンテナに変更されています。例えば、リンクトラッキングコールや、Mobile SDK からのトラッキングアクションコールはすべて、ヒットコンテナに含まれるか除外されます。

## Analysis Workspace のセグメント化

Analysis Workspace には、次の追加機能が含まれます。

- [セグメントを比較](../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)できます。
- フリーフォームテーブルのビジュアライゼーションでディメンションとしてセグメントを使用します。
- [フォールアウト分析](../../analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md)でセグメントを使用できます。

## アドビが提供するセグメント

コンポーネントの左パネルには、作成者と会社が作成したセグメントと、初期設定で提供されているAdobe セグメントが表示されます。 **[!UICONTROL すべて表示]** をクリックすると、通常、これらのセグメントはリストの下部に表示され、![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) で識別されます。

## 順次セグメント {#sequential}

順次セグメントでは、サイト間でのナビゲーションとページビューに基づいて訪問者を識別し、定義済みのアクションとインタラクションのセグメントを提供できます。順次セグメントを使用すると、訪問者が好むものとそうでないものを容易に識別できます。順次セグメントを作成するときは、[!UICONTROL THEN] 演算子を使用して訪問者のナビゲーションを定義し、順序を指定します。

| 訪問 1 | 訪問 2 | 訪問 3 |
|---|---|---|
| 1 回目の訪問では、訪問者はメインランディングページ A にアクセスし、キャンペーンページ B を除き、製品ページ C を閲覧しています。 | 2 回目の訪問では、訪問者は再度メインランディングページ A にアクセスし、キャンペーンページ B を除き、再度製品ページ C にアクセスし、さらに、新しいページ D にアクセスしています。 | 3 回目の訪問では、訪問者は 1 回目および 2 回目の訪問時と同じページに入って同じページをたどり、ページ F を除き、目的の製品ページ G に直接移動しています。 |

次のヒット値に基づく順次セグメントを定義できます。

- ページヒット順序に基づく訪問者：単一の訪問のページビュー、個別訪問間のページビュー、ページビューを除外した訪問。
- ページビュー間またはページビュー後の時間に基づく訪問者：期間終了後、ヒット間、イベント後。

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 訪問者</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">THEN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>
</table>

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 訪問者</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td style="background-color: #D3D3D3;"></td><td>AND</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">THEN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>

<tr>
<td style="background-color: #E5E4E2;"></td><td style="background-color: #D3D3D3;"></td><td>OR</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> ヒット数</td>
</tr>
</tr>
</table>

<!--![](assets/sequential_segmentation_containers_view.png)-->

順次セグメントでは、[!UICONTROL THEN] 演算子を使用したユーザーアクションに基づいてデータセットをフィルターします。

## ハウツーセグメント化のビデオ {#segment-video}

このビデオでは、セグメントコンテナの概要と使用方法を簡単に説明しています。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [セグメントコンテナ](https://video.tv.adobe.com/v/3429100?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## 権限 {#permissions}

+++ **セグメントの使用、作成および管理に必要な権限と許可**

デフォルトでは、すべてのユーザーが個人用のセグメントを作成および編集できます。ただし、管理者の判断により、[セグメントを作成する権限](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=ja)を持つべきユーザーを決定し、特定のグループに割り当てることができます。これらのセグメントは、他の Analytics ユーザーと直接共有できます。

管理者はすべてのセグメントを編集できます。また、グループや組織のメンバー全員とセグメントを共有することもできます。[ セグメント権限（役割別） ](/help/components/segmentation/seg-reference/seg-rights.md)

+++

+++ **社内のすべてのセグメントを表示できますか？**

管理者は、[!DNL Analysis Workspace] ユーザーインターフェイス内ですべてのセグメントを表示できます。

Report Builder には、自分が所有するセグメントと自分が共有しているセグメントが表示されます。

+++

+++ **セグメントマネージャーでは Analytics のセグメントをすべて管理できますか？**

はい、すべてのセグメントをセグメントマネージャーで管理できます。 セグメントマネージャーには、所有者（セグメントを作成したユーザー）、共有ユーザー、管理者ユーザーに表示されるセグメントが表示されます。 セグメントの選択には、ユーザーによって所有および共有されるセグメントが表示されます。

管理者は、Analysis Workspace ユーザーインターフェイス内ですべてのセグメントを表示できます。

Report Builder では、自分が作成したセグメントまたは自分に共有されているセグメントのみが表示されます。

+++

+++ **セグメントを削除できないのはなぜですか？**

セグメントが [Experience Cloudに公開 ](/help/components/segmentation/segmentation-workflow/seg-workflow.md) された場合、セグメントを削除したり、セグメントを編集したりすることはできません。 ただし、セグメントをコピーして、コピーしたバージョンを編集することはできます。

+++
