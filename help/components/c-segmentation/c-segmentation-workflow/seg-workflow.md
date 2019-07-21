---
description: セグメントビルダーによって作成され、セグメントマネージャによって管理されるセグメント用の推奨ワークフローについて説明します。
seo-description: セグメントビルダーによって作成され、セグメントマネージャによって管理されるセグメント用の推奨ワークフローについて説明します。
seo-title: セグメント化ワークフローの概要
solution: Analytics
title: セグメント化ワークフローの概要
topic: セグメント
uuid: e15aaa2f- a604-46dd-9bdd- e2a340c74927
translation-type: tm+mt
source-git-commit: baab08155127871a28a885bbadf21ecaf94ca9d1

---


# セグメント化ワークフローの概要

セグメントビルダーによって作成され、セグメントマネージャによって管理されるセグメント用の推奨ワークフローについて説明します。

## Segmentation workflow overview {#concept_6D2E1A72A3AD4EBBB9135094F2D9DEDF}

セグメントビルダーによって作成され、セグメントマネージャによって管理されるセグメント用の推奨ワークフローについて説明します。

<!-- 

seg_workflow.xml

 -->

![](assets/seg_workflow.png)


![](assets/step1_icon.png)[ セグメントの計画](../../../components/c-segmentation/c-segmentation-workflow/seg-plan.md#concept_D8BE6AB8D8E540E58C3462F9E02F4847)

セグメントの作成、およびセグメント管理環境の設定を行う前に、必要な質問をすべて終えておきます。意図した目的と明確な用途に従ってセグメントを設計します。

セグメントの計画および整理について詳しくは、セグメント計画のチェックリストを参照してください。

![](assets/step2_icon.png) [セグメントの構築](../../../components/c-segmentation/c-segmentation-workflow/seg-build.md#concept_BD4C17B01C5B4E378D0C14C852D055D4)

セグメントを作成し、すべての Analytics 機能で使用できるように編集します。

THEN 演算子を使用したセグメントの作成方法については、[順次セグメント](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_83AEC78CD25F442EBEE364856A889560) の構築を参照してください。

![](assets/step3_icon.png)[ セグメントのタグ付け](../../../components/c-segmentation/c-segmentation-workflow/seg-tag.md#concept_CD892CEB326C4986A1B67487052DBA50)

整理および共有が容易に行えるようにセグメントにタグを付けます。Ad Hoc Analysis のフォルダー階層はタグ付けに置き換えられました。簡易および高度な検索と整理について詳しくは、タグの計画および割り当て方法に関する説明を参照してください。

![](assets/step4_icon.png)[ セグメントの承認](../../../components/c-segmentation/c-segmentation-workflow/seg-approve.md#concept_DF477F151A9E483A92ED1DDAAF035953)

セグメントを正当なセグメントとして承認します。

![](assets/step5_icon.png)[ セグメントの適用](../../../components/c-segmentation/c-segmentation-workflow/t-seg-apply.md#task_13E69C7D428A43EF9CCCA7F1104F1E8F)

レポートのセグメントレール（「表示 セグメント」をクリックして表示）からセグメントを直接適用できます。

![](assets/step6_icon.png) [ セグメントの共有](../../../components/c-segmentation/c-segmentation-workflow/t-seg-share.md#task_7DC54643083E42C28F918E4F0845C5A5)

他の Analytics ツールの特定の閲覧者とセグメントを共有します。また、Adobe Target および Adobe Experience Cloud と共有することもできます。

![](assets/step7_icon.png)[ セグメントのフィルター](../../../components/c-segmentation/c-segmentation-workflow/t-seg-filter.md#task_B59946C6D38945629C1FEACF80A85746)

タグ、所有者およびその他のフィルター（すべてを表示、自分が所有、自分と共有、お気に入りおよび承認済み）でフィルタリングします。

![](assets/step8_icon.png)[ セグメントをお気に入りに登録](../../../components/c-segmentation/c-segmentation-workflow/t-seg-favorite.md#task_F45DFA3FBF0C4082B46A0D032CB20FC5)

セグメントを使いやすく整理するための 1 つの方法として、セグメントをお気に入りに登録することができます。

[セグメントの管理](../../../components/c-segmentation/c-segmentation-workflow/seg-manage.md#concept_7A2E019317864065B7C641DC3315928F)

セグメントマネージャでは、セグメントを様々な方法で管理できます。例えば、共有、フィルターを適用、タグ付け、承認、コピー、削除およびお気に入りへの登録が可能です。