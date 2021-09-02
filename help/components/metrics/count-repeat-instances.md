---
title: 繰り返しインスタンスのカウント
description: レポート内でレポートインスタンスがカウントされるかどうかを指定します。
source-git-commit: e2b38b5b12290ca7da78d00be7b5733303115a03
workflow-type: ht
source-wordcount: '139'
ht-degree: 100%

---


# 繰り返しインスタンスのカウント

[!UICONTROL 繰り返しインスタンスをカウント]：繰り返しインスタンスがレポートまたはプロジェクト内でカウントされるかどうかを指定します。この設定を有効にすると、複数の連続するページビューが複数のページビューと同じページに対して処理されます。この設定を「Off」に設定すると、これらのページビューは単一のページビューとしてカウントされます。この設定は、[!UICONTROL 単一ページ訪問]など、特定の指標にのみ影響します。

Reports &amp; Analytics では、この設定は設定できません。繰り返しインスタンスは、デフォルトで含まれます。
Workspace で、**[!UICONTROL プロジェクト]**／**[!UICONTROL プロジェクト情報と設定]**&#x200B;の下で、[繰り返しインスタンスを含めるまたは除外する](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)ように選択できます。これらはデフォルトで含まれます。

>[!NOTE]
>この設定は、[!UICONTROL フロー]または[!UICONTROL フォールアウト]のビジュアライゼーションには適用されません。Workspace では、[!UICONTROL フロー]には、繰り返しを削除するための独自の[設定](/help/analyze/analysis-workspace/visualizations/c-flow/flow-settings.md)があります。Reports &amp; Analytics では、フローレポートは、デフォルトで常に繰り返しインスタンスを削除しています。
