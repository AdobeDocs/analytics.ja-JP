---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Adobe Analyticsの製品プロファイル

製品プロファイルは、製品管理者が組織内のユーザーに割り当てる権限設定プリセットです。製品プロファイルを作成し、その製品プロファイルにExperience Cloudユーザーを割り当てると、その製品プロファイルに含まれる権限項目が継承されます。

See [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the Enterprise user guide for general information on product profiles.

## 製品プロファイル管理者

製品プロファイル管理者は、その製品プロファイルにユーザーを追加または削除できるオプションのグループです。製品プロファイル管理者は、製品管理者とは異なります。

* 製品プロファイルの管理者は、製品プロファイルのユーザーリストについてのみ責任を負います。
* 製品プロファイル管理者は、Adobe Analyticsにフルアクセスできません。Adobe Analyticsへのフルアクセスは、製品管理者向けに予約されています。
* 製品プロファイル管理者は、製品プロファイルの権限項目を調整できません。製品管理者は、権限項目の調整を行う必要があります。
* 製品プロファイル管理者は、チームのAdobe Analyticsへのアクセス権を付与し管理するだけのチームのリードまたはマネージャーに最適です。個人のシステム管理者または製品管理者がAdobe Analyticsへのアクセス権を付与する必要はありません。

## Adobe Analytics権限項目

Adobe Analyticsにアクセスするために必要な最小限の権限は、製品プロファイルにあります。

* 製品プロファイルに少なくとも1つのレポートスイートにアクセスできる必要があります
* The product profile must belong to the Analytics Tools permission item **Analysis Workspace Access** (or **Reports &amp; Analytics Access**)

### レポートスイート

Analytics組織に属するレポートスイートへのアクセス権を付与します。Adobe Analyticsを使用するには、ユーザーが少なくとも1つのレポートスイートに所属している必要があります。

### 指標

レポートスイート内の指標へのアクセス権を付与します。指標は、Analysis Workspaceでそれぞれのコンポーネントとして表示されます。指標がReports&amp; Analyticsで利用可能な場合、サイト指標の下のメニュー項目として使用できます。

カスタム指標には「カスタムイベント1~1000"というラベルが付けられ、レポートスイートとは独立して保持されます。「カスタムイベント1"が有効な権限項目である場合、そのユーザーは製品プロファイル内のすべてのレポートスイートのevent1にアクセスできます。

### ディメンション

レポートスイートのディメンションに対するアクセス権を付与します。ディメンションは、Analysis Workspaceでそれぞれのコンポーネントとして表示されます。また、ディメンションがReports&amp; Analyticsで利用できる場合は、メニュー項目として使用できます。

eVarなどのカスタム変数は、レポートスイートとは独立して保持されるように「カスタムコンバージョン1~250"というラベルが付けられます。「カスタムコンバージョン1"が有効な権限項目である場合、そのユーザーは製品プロファイル内のすべてのレポートスイートのeVar1にアクセスできます。

### レポートスイートツール

レポートスイートツールの権限項目では、ユーザーがアクセスできるレポートスイートに固有の機能へのアクセス権を付与します。See [Report Suite Tools](report-suite-tools.md) for a full list of permission items and descriptions.

### Analytics ツール

Analyticsツールの権限項目では、レポートスイートの設定に依存しない機能へのアクセス権を付与します。See [Analytics Tools](analytics-tools.md) for a full list of permission items and descriptions.

## 製品プロファイル開発者

Developers are similar to users, except they are granted the ability to use the Experience Cloud API on Adobe I/O. See [Manage Developers](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Enterprise user guide for more information.
