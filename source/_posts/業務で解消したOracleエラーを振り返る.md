---
title: 業務で解消したOracleエラーを振り返る
date: 2021-02-03 00:00:00
tags:
---
## はじめに
最近の業務で解消したOracleエラーを振り返ります。

## Oracleのバージョン
12c

## エラーコード
### ORA-00054
- 詳細
> ORA-00054: resource busy and acquire with NOWAIT specified or timeout expired
> Cause: Interested resource is busy.
> Action: Retry if necessary or increase timeout.
（翻訳）
> ORA-00054: リソースがビジー状態で、NOWAITが指定されているか、タイムアウトが切れている状態で取得しました。
> 原因: リソースがビジー状態です。
> アクション: 必要に応じて再試行するか、タイムアウトを増やしてください。

- 直接的な原因
原因は、TRUNCATE TABLEを実行するときに前のトランザクションが終了していなかったことです。前のトランザクションが終了していなかった原因は、パフォーマンスの悪いSELECT文で数万件のレコードを処理しようとしたことです。
- 対処
SELECT文のパフォーマンスを改善しました。

### ORA-01861
- 詳細
> ORA-01861: literal does not match format string
> Cause: Literals in the input must be the same length as literals in the format string (with the exception of leading whitespace). If the "FX" modifier has been toggled on, the literal must match exactly, with no extra whitespace.
> Action: Correct the format string to match the literal.
（翻訳）
> ORA-01861: リテラルがフォーマット文字列と一致しない
> 原因: 入力のリテラルは、フォーマット文字列のリテラルと同じ長さでなければなりません（先頭の空白を除いて）。FX" 修飾子がトグルされている場合、リテラルは正確に一致しなければなりません。
> アクション: フォーマット文字列をリテラルと一致するように修正します。

- 直接的な原因
原因は、1つのSELECT文の中で、TO_DATE関数に日付書式を指定がある場合とない場合が混在していたことでした。日付書式の指定がない場合には、暗黙の型変換が行われ、日付書式を指定した場合とは別の書式が設定されていました。
- 対処
SELECT文中のすべてのTO_DATE関数使用時に、日付書式を指定するようにしました。

### ORA-00933
- 詳細
> ORA-00933: SQL command not properly ended
（翻訳）
> ORA-00933. SQLコマンドが正しく終了しない
- 直接的な原因
原因は、SQL文をJavaのプロパティファイルに記載するためにDBViewerで非整形文にした後、末尾の”;”を削除し忘れたことです。末尾に’;’があると、環境によってはエラーが発生します。エラーは例えばSQL文をODBCから呼び出して使う際に発生します。SQL文をSQL*PlusやDBViewerから直接実行するときは発生しません。
- 対処
末尾の’;’を削除しました。

## 最後に
Oracleのエラーは環境によって発生有無が変化するので注意が必要です。
エラーを振り返ることで、知識に肉付けができます。

## 参考資料
https://docs.oracle.com/cd/E82638_01/errmg/index.html

