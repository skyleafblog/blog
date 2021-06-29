---
title: Excel VBAで「全シートCtrl + Home」を自動化する
date: 2021-02-03 00:00:00
tags:
---

## はじめに
- Excel VBAで作業を自動化するまでの手順を解説します。
- 「全シートCtrl + Home」をするとExcelでファイルを開いた人が少し見やすくなります。

## Exce VBAを使用するための準備
1. Excelのブックで開発を有効にする
※ 「ファイル」タブ→「オプション」→「リボンのユーザー設定」から有効にできる

2. Alt + F11でVBAを開く

3. ツールのオプションで、「自動構文チェック」を外し、「変数の宣言を強制する」をチェック

4. 挿入から標準モジュールを追加

5. 標準モジュールに以下を記述
```
Sub ctrlHome()

End Sub
```
※End Subは「sub ctrlHome」と打ってEnterを押せば補完される

## Ctrl + Homeを実現する
1. Ctrl + Homeを実現する方法を調べる
※今回はまずExcelの機能を使って調べる

2. 開発タブで「マクロの記録」を選択、必要事項を記入

3. ブックに戻り、新しいシートを作成し、開いておく

4. Ctrl + HomeとCtrl + pg upを手作業で行う

5. 開発タブで「記録終了」を選択

6. VBAに戻り、記録されたコードを確認

7. 手順10を参考にCtrl + Homeを実行するコードを手順5で記述したSubの中に書く
※ 最後に先頭のシートに戻る処理も書くと便利

8. F8でステップ実行（動作確認）

9. 手順10とネット検索を頼りに全シートで手順11を実行するためのコードを書く
- 例
```
Option Explicit

Sub ctrlHome()

    Dim i As Integer

    For i = 1 To Sheets.Count
        Sheets(i).Select
        Range("A1").Select
    Next
    
    Sheets(1).Select
    
End Sub
```
- 各記述の簡単な説明

> Option Explict
変数宣言の必須化（変数定義忘れを防ぐ）

> Dim i As Integer
変数iをInteger型で宣言する

> For i = 1 To Sheets.Count
> Next
最後のシートまで繰り返す

> Sheets(1).Select
最初のシートを選択する

10. F8でステップ実行（動作確認）、問題なければF5で実行

11. ブックに戻り、「名前をつけて保存」からマクロ有効ブックを選択し、保存

## 最後に
- シンプルな記述でCtrl + Homeの自動化ができます。
- 同様の手順で様々な操作が自動化できます。



