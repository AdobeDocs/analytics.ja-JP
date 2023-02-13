---
source-git-commit: d8442f1ec8f35fbcda98b35070936677813ce330
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 16%

---
# スニペット

## Reports &amp; Analytics の提供終了に関するお知らせ {#ra-eol}

>[!IMPORTANT]
>
>詳しくは、Reports &amp; Analytics の[提供終了のお知らせ](https://express.adobe.com/page/6WnF8JK6IRDhf/)を参照してください。

## データ辞書のフィルター条件 {#dd-filter-criteria}

1. （オプション） **フィルター** アイコン ![データ辞書フィルターアイコン](/help/analyze/analysis-workspace/components/data-dictionary/assets/data-dictionary-filter-icon.png)次に、次のいずれかのフィルターオプションを選択して、コンポーネントのリストをフィルターします。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **承認済み**] | 管理者によって「承認済み」とマークされたコンポーネントのみを表示します。 |
   | [!UICONTROL **お気に入り**] | [ お気に入り ] の一覧にあるコンポーネントのみを表示します。 お気に入りのリストにコンポーネントを追加する方法については、 [コンポーネントの概要](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **ディメンション**] | Dimension ( このオプションは、 [!UICONTROL **クイックフィルター**] 」タブに表示されます )。 |
   | [!UICONTROL **指標**] | 指標のコンポーネントのみを表示します。 ( このオプションは、 [!UICONTROL **クイックフィルター**] 」タブに表示されます )。 |
   | [!UICONTROL **セグメント**] | セグメントのコンポーネントのみを表示します。 ( このオプションは、 [!UICONTROL **クイックフィルター**] 」タブに表示されます )。 <!--this is Filters in CJA--> |
   | [!UICONTROL **日付範囲**] | 日付範囲のコンポーネントのみを表示します。 ( このオプションは、 [!UICONTROL **クイックフィルター**] 」タブに表示されます )。 |
   | [!UICONTROL **すべてを表示**] | すべてのコンポーネントを表示 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **未承認**] | 管理者によってまだ承認済みとマークされていないコンポーネントのみを表示します。 管理者は、レビューと承認が必要なコンポーネントを識別する際に役立ちます。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **説明がありません**] | 「説明」フィールドに、まだ説明を持たないコンポーネントのみを表示します。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **重複を表示**] | 選択したレポートスイート内の別のコンポーネントと同じラベルまたは説明を持つコンポーネントのみを表示します。 重複として表示するには、ラベルまたは説明が完全に一致する必要があります。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **最近のデータがありません**] | 過去 90 日間にデータを収集していないコンポーネントのみを表示します。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **作成者Adobe**] <!-- I don't see this option--> | Adobeが作成したコンポーネントのみを表示 管理者または組織内の別のユーザーが作成したコンポーネントは表示されません。 |

   {style=&quot;table-layout:auto&quot;}

## データディクショナリコンポーネント情報 {#dd-component-information}

| オプション | 関数 |
|---------|----------|
| [!UICONTROL **承認済み**] | コンポーネントが管理者によってレビューおよび承認されたことを示します。 管理者向けに、 [!UICONTROL **承認が必要です**] オプションが表示されます。 このオプションを選択すると、それが「承認済み」とマークされます。 |
| [!UICONTROL **説明**] | コンポーネントの意図された機能を表します。 ( この情報は、Analytics 管理者によって追加されます。詳しくは、 [コンポーネントの説明を追加](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **次によく使用される**] | <p>表示しているコンポーネントで最もよく使用されるコンポーネントを表示します。</p><p>5 つの主要なコンポーネントタイプに対して、最大 5 つのコンポーネントが表示されます。指標、計算指標、Dimension、セグメント、日付範囲。</p><p>このリストは、過去 90 日間のデータに基づいています。 表示にアクセスできるコンポーネントのみが表示されます。 <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **次に類似している**] | <p>表示しているコンポーネントと同様のラベルを持つコンポーネントを表示します。</p><p>5 つの主要なコンポーネントタイプに対して、最大 5 つのコンポーネントが表示されます。指標、計算指標、Dimension、セグメント、日付範囲。</p><p>表示にアクセスできるコンポーネントのみが表示されます。</p><p>レポートスイート内の重複するコンポーネントは、ここに表示されます。 Analytics 管理者は、 [データ辞書の正常性の監視](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md). <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **タグ**] | コンポーネントに適用されているすべてのタグを表示します。 管理者アクセス権を持つユーザーは、コンポーネントの編集時にタグを追加できます。 |
| [!UICONTROL **コンポーネントの種類**] | コンポーネントのタイプが、Dimension、指標、セグメント、日付範囲のどれであるかを示します。 |
| [!UICONTROL **作成者**] | コンポーネントを作成したユーザーの名前を表示します。 |
| [!UICONTROL **プレビュー**] | Analysis Workspaceでのコンポーネントの外観のプレビューを表示します。 |
| [!UICONTROL **最終変更日**] | コンポーネントが最後に変更された日を表示します。 このセクションは、セグメント、計算指標および日付範囲を表示する場合に表示されます。 <!--for CJA, it is displayed for all components--> |

{style=&quot;table-layout:auto&quot;}

## リリース段階の限定的なテスト {#release-limited-testing}

>[!AVAILABILITY]
>
>この記事で説明する機能は、リリースの制限付きテスト段階にあり、お使いの環境ではまだ使用できない場合があります。 このメモは、機能が一般入手可能になったら削除されます。Analytics リリースプロセスについて詳しくは、[Adobe Analytics 機能リリース](/help/release-notes/releases.md)を参照してください。

## リリース段階の限定的なテストセクション {#release-limited-testing-section}

>[!AVAILABILITY]
>
>この節で説明する機能は、リリースの制限付きテスト段階にあり、お使いの環境ではまだ使用できない場合があります。 このメモは、機能が一般入手可能になったら削除されます。Analytics リリースプロセスについて詳しくは、[Adobe Analytics 機能リリース](/help/release-notes/releases.md)を参照してください。

