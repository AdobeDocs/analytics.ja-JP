---
description: page_event の値に基づいてヒットタイプを判別する参照テーブル。
keywords: データフィード；ページ；イベント；ページイベント;post_page_イベント
title: ページイベント参照
feature: Reports & Analytics Basics & Analytics Basics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 93%

---

# ページイベント参照

page_event の値に基づいてヒットタイプを判別する参照テーブル。

| ヒットタイプ | `page_event` の値 | `post_page_event` の値 |
| --- | --- | --- |
| ページビュー数 | 0：モバイル SDK のすべてのページビューコールと `trackState` コール | `post_page_event` と同じ値 |
| リンクトラッキング | 10：モバイル SDK のカスタムリンクと `trackAction` コール<br>11：ダウンロードリンク<br>12：出口リンク | 100：モバイル SDK のカスタムリンクと `trackAction` コール<br>101：ダウンロードリンク<br>102：出口リンク |
| マイルストーンビデオ | 31：メディア開始<br>32：メディアの更新（他の変数処理なし）<br>33：メディアの更新（他の変数を使用） | 76：メディア開始<br>77：メディアの更新（他の変数処理なし）<br>78：メディアの更新（他の変数を使用） |
| ハートビートビデオ | 50：メディアストリーム開始（Primetime 以外）<br>51：メディアストリーム終了（Primetime 以外）<br>52：メディアストリームスクラビング（Primetime 以外）<br>53：メディアストリームキープアライブ（Primetime 以外）<br>54：メディアストリーム広告開始（Primetime 以外）<br>55：メディアストリーム広告終了（Primetime 以外）<br>56：メディアストリーム広告スクラビング（Primetime以外）<br>60：Primetime メディアストリーム開始<br>61：Primetime メディアストリーム終了<br>62：Primetime メディアストリームスクラビング<br>63：Primetime メディアストリームキープアライブ<br>64：Primetime メディアストリーム広告開始<br>65：Primetime メディアストリーム広告終了<br>66：Primetime メディアストリーム広告スクラビング | `post_page_event` と同じ値 |
| 調査 | 40：調査から生成された任意の呼び出し | 80：調査から生成された任意の呼び出し |
| Analytics for Target | 70：ヒットに Target アクティビティデータを含む | `post_page_event` と同じ値 |
