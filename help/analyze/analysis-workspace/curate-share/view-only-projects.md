---
description: Analysis Workspaceの読み取り専用プロジェクトのエクスペリエンスについて説明します。
keywords: 読み取り専用プロジェクト
title: 読み取り専用プロジェクト
feature: Curate and Share
role: User, Admin
exl-id: 53372247-6902-4c7f-9132-38a1d453186c
TQID: https://experienceleague.adobe.com/8PyU15pb5sDqq-qZE-T8ceuDJdXDUXyxPQvJYJGUfwg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: dcae653e-62c6-4cc8-84e6-ee110b848296id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 52%

---

# 読み取り専用プロジェクト

[共有機能](share-projects.md)を使用して、プロジェクトを受信者に読み取り専用として共有できます。 **[!UICONTROL 読み取り専用]**&#x200B;の役割に配置された受信者は、より限定的なプロジェクト体験を受け取ることができます。

組織のデータ構造、Analysis Workspace または Adobe Analytics 全般に慣れていないユーザーにプロジェクトを共有し、安全な環境でデータやインサイトを利用してもらいたい場合には、この方法が適しているかもしれません。

![読み取り専用として共有](assets/read-only-project-sender.png)

読み取り専用の受信者のインタラクションは制限されています。

![読み取り専用として共有](assets/read-only-project-receiver.png)

## 無効な操作

表示のみのプロジェクトで無効になる操作には、次のものが含まれます。

* 非表示の左パネル
* パネルカレンダーの日付範囲 注意：受信者にカレンダーコントロールを付与する場合は、日付範囲](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=ja)の[ ドロップダウンセグメントを追加します。
* フリーフォームセグメンテーション
* 表示可能な行のフリーフォーム数
* フリーフォーム行、列またはビジュアライゼーションの設定
* パネルセグメント
* 編集、挿入、コンポーネントメニュー
* Workspace のヒント

## 有効な操作

表示のみのプロジェクトで有効になっているインタラクションのいくつかは、次のとおりです。

| 面グラフ | 有効な操作 |
| --- | --- |
| **フリーフォームテーブル** | <li>ページネーションと並べ替え</li><li>ホバリング</li><li>リンクされたビジュアライゼーションを更新するセル選択</li><li>コンテキストメニュー/ビジュアライゼーションリンクの取得</li><li>コンテキストメニュー/クリップボードにコピー</li> |
| **ビジュアライゼーション** | <li>クリックして凡例のオン／オフを切り替え</li><li>ホバリング</li><li>コンテキストメニュー/ビジュアライゼーションリンクの取得</li><li>折りたたみ／展開</li><li>フロー — フローノードを展開</li><li>マップ — ズーム</li></ul> |
| **パネル** | <li>インタラクティブなドロップダウンセグメント</li><li>コンテキストメニュー/パネルリンクを取得から</li><li>折りたたみ／展開</li> |
| **プロジェクト** | <li>すべての情報アイコンの検査</li><li>プロジェクトメニュー — 新規、開く、ランディングページとして設定、更新、CSV／PDF をダウンロード、限られたプロジェクト情報および設定</li><li>共有メニュー — プロジェクトリンクを取得、今すぐファイルを送信</li><li>ヘルプメニュー — 「ヒント」および「デバッガー」オプション以外のすべてのアクション</li> |


## 誰でも共有できるエクスペリエンス

[誰とでも共有](share-projects.md#share-a-project-with-anyone-no-login-required)を使用してプロジェクトを選択した場合、リンクの受信者はプロジェクトを表示するだけで、プロジェクトを操作することはできません。

![誰とでも共有](assets/share-with-anyone-receiver.png)
