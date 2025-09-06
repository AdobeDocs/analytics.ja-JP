---
description: Analysis Workspace のアクセシビリティサポート機能について説明します。
title: Analysis Workspace のアクセシビリティ
feature: Workspace Basics
role: User, Admin
exl-id: 2bacbee8-097c-4fc5-8be4-7e4f284db08c
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 100%

---


# Analysis Workspace のアクセシビリティ

Customer Journey Analytics の主要な分析ツールである [!UICONTROL Analysis Workspace]のアクセシビリティサポートについて説明します。

アクセシビリティとは、視覚障害、聴覚障害、認知障害、身体障害などの障害を持つユーザーに対して、製品を使用できるようにすることです。ソフトウェア製品のアクセシビリティ機能の例を次に示します。

* スクリーンリーダーのサポート
* グラフィックの代替テキスト
* キーボードショートカット
* ディスプレイカラーの高コントラストへの変更
* その他の機能

[!UICONTROL Analysis Workspace] には、次のような、使いやすいツールが用意されています。

## キーボードナビゲーション

[!UICONTROL Analysis Workspace] でのナビゲーションは、上から下、左から右です。次のナビゲーション要素はアクセシビリティを向上します。

* **[!UICONTROL タブ]**&#x200B;キーを押すと、Workspace 内の大きなセクション間を移動するランドマークショートカットが有効になります。左パネルでは、**[!UICONTROL タブ]**&#x200B;を使用して、ドラッグ可能なオプション間を移動することもできます。
* **[!UICONTROL タブ]**&#x200B;キーで要素がハイライト表示されたら、◀ と ▶ で個々の要素間を移動します。
* **[!UICONTROL F6]** キーを押すとプロジェクト内の最初のパネルに移動し、そのパネル内のビジュアライゼーション間を移動します。その後、プロジェクト内の次のパネルに移動し、同じ動作を繰り返します。
* フォーカスインジケーターを適用して、目が見えるキーボードユーザーに現在どの UI 要素にフォーカスがあるかを明確に示します。インジケーターは、フォーカスされたパネルの青色の境界線です。最近選択された機能と機能内の選択は、灰色の背景で表示されます。この例では、[!UICONTROL コンポーネント]とページディメンションが最近選択されています。

  ![フリーフォームテーブル周囲の青い境界線のフォーカスインジケーターを表示するフリーフォームテーブル。](assets/focus-indicator.png)

### メニューバーのキーボードナビゲーション

1. メニューバーに到達するまで Tab キーを押します。
1. 矢印キーを使用して、メニューとメニュー項目間を移動します。
1. **[!UICONTROL Enter]** キーを押してメニューを開くか、メニュー項目を選択します。
1. メニューを閉じるには **[!UICONTROL Esc]** キーを使用します。

### ドラッグ&amp;ドロップ操作のキーボードナビゲーション

[!UICONTROL Analysis Workspace] は、ドラッグ＆ドロップによるユーザーインターフェイスです。ただし、ユーザーは、代わりにキーボードを使用してコンポーネントを追加できます。

1. タブを押して左パネルのコンポーネントに移動します。
1. **[!UICONTROL Enter]** キーを押して選択します。
1. 矢印キーを使用して、コンポーネントをドロップする領域に移動します。
1. **[!UICONTROL Enter]** キーを押して、コンポーネントを配置します。

### キーボードショートカット（ホットキー）

[!UICONTROL Analysis Workspace] は、シームレスなワークフローを実現する豊富な[キーボードショートカット（ホットキー）](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)のセットを備えています。

## スクリーンリーダーとスクリーン拡大鏡のサポート

スクリーンリーダーは、コンピューターの画面に表示されるテキストを読み上げます。また、アプリケーション内のボタンラベルや画像の説明など、テキスト以外の情報も読み上げます。

## カラーパレットとコントラスト

[!UICONTROL Analysis Workspace] は、WCAG 2.1 AA への準拠を目指しています（カラーコントラストの要件を含む）。

また、プロジェクトに対しては、**[!UICONTROL プロジェクト]**／**[!UICONTROL プロジェクト設定]**／[プロジェクトのカラーパレット](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md)で、ユーザーが希望するカラーパレットを設定できます。

## 必須の検証

コンポーネント、ビジュアライゼーションまたはパネルを作成する場合、保存時に必須フィールドが検証されます。必須フィールドが検証に合格しない場合は、赤色の枠線にエラーアイコンが表示されます。記述された説明には、修正が必要な事項について説明されています。

![セグメントビルダーとエラー検証インジケーター。](assets/error-validation.png)

## オペレーティングシステムのアクセシビリティ機能のサポート

Analysis Workspace は、Windows と macOS のビルトインのアクセシビリティ機能（高コントラストモード、スティッキーキー、スローキーやフィルターキーなど）をサポートしています。また、ユーザーインターフェイスに関する情報もオペレーティングシステムに提供し、macOS の VoiceOver や Windows の NVDA などのスクリーンリーダーを含む支援テクノロジーとの対話を実現します。


<!--

# Accessibility in Analysis Workspace

Learn about accessibility support in [!UICONTROL Analysis Workspace], the premier analysis tool for Adobe Analytics. 

Accessibility refers to making products usable for people with visual, auditory, cognitive, motor, and other disabilities. Examples of accessibility features for software products include screen reader support, text equivalents for graphics, keyboard shortcuts, change of display colors to high contrast, and so on. 

[!UICONTROL Analysis Workspace] provides some tools that make it accessible to use, including:

## Navigate [!UICONTROL Workspace] using the keyboard

Navigation in [!UICONTROL Analysis Workspace] works top > down, and left > right. The following navigational elements facilitate accessibility:

* The `Tab` key enables landmark shortcuts, moving between larger sections within Workspace. In the left rail, `Tab` also enables you to move from one draggable option to the next.
* The `left/right arrows` move between individual elements after `Tab` has highlighted it. 
* The `F6` navigates to the first panel in the project and  moves between the visualizations within that panel. Then, it moves to the next panel in the project and repeats. 
* We apply focus indicators so that sighted keyboard users have a clear indication of which UI element currently has focus. The indicator is a blue border around the selected element.

    ![Focus Indicator](assets/focus-indicator.png)

### Keyboard navigation for the menu bar 

1. Tab until you have reached the menu bar.
1. Use left/right arrow keys to navigate to the menu you want.
1. Press `Enter` to select the menu and show its options.
1. Use up/down arrow keys to navigate to the menu option you want.
1. Press `Enter` to select the option.

### Keyboard navigation for drag & drop interactions 

[!UICONTROL Analysis Workspace] is a drag & drop user interface. However, users can add components using the keyboard instead:

1. Tab to a component in the left rail.
1. Press `Enter` to select.
1. Use arrow keys to navigate to the area where you want to drop the component.
1. Press `Enter` to place the component.

### Keyboard shortcuts (hotkeys) 

[!UICONTROL Analysis Workspace] offers a rich set of [keyboard shortcuts](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) for a more seamless workflow. Some common shortcuts for navigation, analysis creation, and insight democratization are listed below. 

#### Navigation

| Shortcut | Action |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Jump to different rails: [!UICONTROL Panels], [!UICONTROL Visualizations], or [!UICONTROL Components] | 
| `[Alt + Left / Right]` | Navigate between panels |
| `[Alt + M]` | Collapse/expand all panels |
| `[Alt + Ctrl + M]` | Collapse/expand active panel |
| `[Ctrl + /]` | Search left rail |

#### Analysis creation

| Shortcut | Action |
| --- | --- |
| `[Alt + 1]` | New freeform table |
| `[Ctrl + Shift + C]` | New calculated metric |
| `[Ctrl + Shift + D]` | New date range |
| `[Ctrl + Shift + E]` | New segment |
| `[Ctrl + Z]` | Undo |
| `[Component drag + Shift]` | Create a drop-down filter |

#### Democratization

| Shortcut | Action |
| --- | --- |
| `[Ctrl + S]` | Save |
| `[Ctrl + Shift + G]` | Curate |
| `[Ctrl + G]` | Share |
| `[Alt + Shift + S]` | Schedule |
| `[Alt + L]` | Get link to project |
| `[Ctrl + Shift + B]` | Download PDF |

## Support for screen readers and screen magnifiers

A screen reader reads text that appears on the computer screen. It also reads non-textual information, such as button labels or image descriptions in the application, provided in accessibility tags or attributes.  

## Color palettes & contrast  

[!UICONTROL Analysis Workspace] strives for WCAG 2.1 AA conformance, including requirements for color contrast. 

In addition, users can set their own preferred color palette for a project under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md). 

## Required field validation in component builders 

When building a component, required fields are validated when you save. If a required field does not pass validation, it will be outlined in red with an error icon. A written description appears of the issue that needs to be fixed.  

Once a component is fully validated, pressing `Save` closes the builder. 

![Error validation](assets/error-validation.png)

## Support for operating system accessibility features  

Analysis Workspace supports built-in MS Windows and macOS accessibility features like high-contrast mode, sticky keys, and slow keys/filter keys. It also provides information about the user interface to the operating system to enable interaction with assistive technologies, including screen readers such as VoiceOver for macOS and NVDA on Windows.

-->