---
description: 新しいアカウントの設定、トラフィックスパイク、トラフィック増加について、アドビに事前に通知する必要があります。遅延やシステム全体への悪影響の可能性を最小限に抑えるため、ハードウェアを事前に割り当てる必要があるためです。
title: トラフィック増加に対して必要なリードタイム
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 55c8337dbeebcc76db367ead15128c095e4d8ce5
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 77%

---

# トラフィック増加に対して必要なリードタイム

## トラフィック増加に対して必要なリードタイム

新しいアカウントの設定、トラフィックスパイク、トラフィック増加について、アドビに事前に通知する必要があります。遅延やシステム全体への悪影響の可能性を最小限に抑えるため、ハードウェアを事前に割り当てる必要があるためです。

Reports &amp; Analytics ユーザーインターフェイスを通じてアラートを送信することによって、ハードウェアの割り当てが進められます。

>[!IMPORTANT]
>
> アドビは、「プレースホルダー」のトラフィック変更リクエストに対応できません。特に指示のない限り、アラートを早く送信しすぎないことを含め、できる限り推奨リードタイムを守ってください。

次のガイドラインを使用して、どの程度事前にトラフィックアラートを送信する必要があるかを決定します。

### ハードウェア割り当てのリードタイム


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> トラフィック変更タイプ </th>
   <th colname="col2" class="entry"> 必要なリードタイム </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 新しいアカウント設定 </td>
   <td colname="col2"> <ul><li>3 営業日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 過去 30 日間に比べ、1 日の平均ボリュームでトラフィックの急増または急激な恒常的なトラフィックの増加が 25%に達しました。</td>
   <td colname="col2"> <ul><li>1 日に 1 億ヒット未満のレポートスイート：通知は不要</li><li>1 日に 1 億件を超えるヒットを含むレポートスイート：5 営業日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 過去 30 日間に対する、1 日の平均ボリュームでのトラフィックの急増または 1 日あたり 25%以上の恒常的なトラフィックの増加</td>
   <td colname="col2"> <ul><li>5 営業日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> ホリデーイベント 10 月～ 12 月 </td>
   <td colname="col2"> <ul><li>1 か月</li></ul> </td>
  </tr>
 </tbody>
</table>

その他の考慮事項：

* 上昇または増加し始めているレポートスイートがいくつかあり、予測トラフィックの合計が前述の数値の範囲にある場合、各レポートスイートの予測トラフィックの合計としてリードタイムが適用されます。
* 次の情報を利用可能にして、トラフィックの変更を送信できます。

   * レポートスイート ID
   * 1 日あたりの予測ヒット数
   * Go Live 日

* トラフィックが減少、またはレポートスイートが非推奨の場合もクライアントアラートが必要です。

### トラフィックが実現しなかったことによるハードウェアの割り当て解除

クライアントアラートで予測されたトラフィックが「Go Live 日」から 4 週間以内に実現しない場合、新しいアカウント、トラフィックスパイク、トラフィック増加用のハードウェアの割り当ては解除されます。引き続きトラフィックが予想される場合、トラフィックが増加したら新しいクライアントアラートを生成する必要があります。