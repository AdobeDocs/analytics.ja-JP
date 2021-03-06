---
title: Adobe Analytics の製品プロファイル
description: 製品管理者が組織内のユーザーに割り当てる権限プリセットとして製品プロファイルを使用する方法について説明します。
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
source-git-commit: 8f25dfefbc6fba1fb525d2e9e0fce654e21ef362
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 95%

---

# Adobe Analytics の製品プロファイル

製品プロファイルは、製品管理者が組織内のユーザーに割り当てることができる権限プリセットです。製品プロファイルを作成し、その製品プロファイルに Experience Cloud ユーザーを割り当てると、ユーザーは製品プロファイルに含まれる権限項目を継承します。

製品プロファイルの一般情報については、エンタープライズユーザーガイドの[製品とプロファイルの管理](https://helpx.adobe.com/jp/enterprise/using/manage-products-and-profiles.html)を参照してください。

## 製品プロファイル管理者

製品プロファイル管理者は、製品プロファイルに対するユーザーの追加または削除をおこなえるオプションのグループです。製品プロファイル管理者は、製品管理者とは異なることに注意してください。

* 製品プロファイル管理者は、Adobe Analytics に対するフルアクセス権を持っていません。Adobe Analytics へのフルアクセスは、製品管理者用に予約されています。
* 製品プロファイルの管理者は、製品プロファイルの権限項目を調整できます。
* 製品プロファイルの管理者は、製品プロファイルをユーザーグループに割り当てたり、ユーザーグループから削除したりできます。
* 製品プロファイル管理者は、チームの Adobe Analytics へのアクセスを許可および管理する必要があるチームのリーダーやマネージャーに最適です。システム管理者や製品管理者の手を借りなくても、個人が Adobe Analytics へのアクセスを許可することができます。

## Adobe Analytics 権限項目

Adobe Analytics にアクセスするためには、製品プロファイルで最低限、次の権限が必要となります。

* 製品プロファイルは、少なくとも 1 つのレポートスイートにアクセスできる必要があります
* 製品プロファイルは、Analytics ツール権限項目の **Analysis Workspace Access**（または **Reports &amp; Analytics Access**）に属している必要があります

### レポートスイート

Analytics 組織に属するレポートスイートへのアクセスを許可します。ユーザーが Adobe Analytics を使用するには、1 つ以上のレポートスイートに属している必要があります。

### 指標

レポートスイート内の指標へのアクセスを許可します。指標は、Analysis Workspace のそれぞれのコンポーネントにリストされるか、Reports &amp; Analytics で指標を利用できる場合はサイト指標のメニュー項目として利用できます。

レポートスイートから独立させるため、カスタム指標には「カスタムイベント 1 ～ 1000」というラベルが付けられます。「カスタムイベント 1」が有効な権限項目である場合、そのユーザーは製品プロファイル内のすべてのレポートスイートの event1 にアクセスできます。

### ディメンション

レポートスイートのディメンションへのアクセスを許可します。ディメンションは、Analysis Workspace のそれぞれのコンポーネントにリストされるか、Reports &amp; Analytics でディメンションを利用できる場合はメニュー項目として利用できます。

eVar などのカスタム変数には、レポートスイートから独立させるため、「カスタムコンバージョン 1 ～ 250」というラベルが付けられます。「カスタムコンバージョン 1」が有効な権限項目である場合、そのユーザーは製品プロファイル内のすべてのレポートスイートの eVar1 にアクセスできます。

### レポートスイートツール

レポートスイートツールの権限項目は、ユーザがアクセスできるレポートスイートに固有の機能へのアクセス権を付与します。権限項目と説明の完全なリストについては、[レポートスイートツール](report-suite-tools.md)を参照してください。

### Analytics ツール

Analytics ツールの権限項目は、レポートスイートの設定に依存しない機能へのアクセスを提供します。権限項目と説明の完全なリストについては、[Analytics ツールの製品プロファイル権限](analytics-tools.md)を参照してください。

## 製品プロファイル開発者

開発者はユーザーに似ていますが、ユーザー開発者にExperience CloudAPI を使用する権限が付与されています。 詳しくは、 [開発者の管理](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html) （エンタープライズユーザーガイド）を参照してください。 プロファイルに対する開発者アクセス権限を付与されているユーザーは、開発コンソール（console.adobe.io）にアクセスし、Adobe Analytics 統合を編集できます。ユーザーに対して承認された Analytics API の呼び出しと応答は、そのユーザーが開発者アクセス権を持っているすべてのプロファイルの正味権限に依存します。

例えば、すべての指標、すべてのディメンション、1 つのレポートスイートを含むプロファイル権限を持っている場合、プロファイルの開発者アクセスメンバーは、関連スイート内の任意のコンポーネントに関する API 呼び出しをおこなうことができます。異常値検出を追加すると、レポートに異常値データを追加して、より完全な応答を含めることができます。一般的に、プロファイルが Adobe Analytics インターフェイス内のシナリオへのアクセスを許可した場合、同様に定義されたプロファイル上の開発者アクセスにより、対応する API の呼び出しと応答が有効になります。
