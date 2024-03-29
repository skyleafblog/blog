---
title: Eclipseの操作を倍速にする
date: 2022-10-28 16:30:03
tags:
---

# 本記事の目的
私たちエンジニアは、割り振られた作業で手いっぱいの中、不測の事態には調査も即座に行えなければなりません。
また、他人に教授を仰ぎたい時、IDEの操作が遅いゆえに時間を無碍に奪ってしまう問題もあるのです。

そこで本記事では、Eclipseの操作を倍速化することでコーディングの速度と操作の向上を目指します。

## ECLIPSEの操作を効率化する
ECLIPSEのショートカットキーを使いながら学びましょう。

### 1. Javaプロジェクトを作成
プロジェクト「操作練習」を作成します。
#### `Ctrl + N`
![新規作成ウィザード](/image/コーディングを倍速にする/create_project.png)
プロジェクトと同じ要領でMainクラスも作成します。
![Mainクラス](/image/コーディングを倍速にする/view_class.png)

### 2. 予測からコードを補完
エントリーポイントである`public static void main(String[] args)`を予測候補から補完します。
#### `Ctrl + Space`
mainまで入力して`Ctrl + Space`で"main"から予測される定型文やクラス、メソッド候補を補完することが出来ます。
![予測表示](/image/コーディングを倍速にする/predict_code.png)

### 3. ファイル内検索
表示中のファイル内から特定の文字列を検索できます
#### `Ctrl + F`
![ファイル内検索](/image/コーディングを倍速にする/find_string.png)
置換処理もできます。
![置換処理](/image/コーディングを倍速にする/replace.png)

### 4. 自動インポート
コーディングしたクラスからパッケージを予測して自動でインポートを補完します。
#### `Ctrl + Shift + O`

### 5. フォーマット
インデントや改行を自動で訂正します。
#### `Ctrl + Shift + F`

### 6. ブロックの開始・終了に移動
ブロックの開始・終了行にジャンプします。
#### `Ctrl + Shift + P`

### 7. メソッドの宣言部に移動
フォーカス行のメソッドの宣言部にジャンプします
#### `Ctrl + Shift + ↑`

### 8. 呼び出し先に移動
フォーカス中のクラスやメソッド、変数の呼び出し箇所にジャンプします
#### `F3`

### 9. 前回いた場所に移動
前回までにいた場所に戻ります。
#### `Alt + ←`

### 10. 現在地点より未来にいた場所に進む
`Alt + ←`で戻った地点を現在地点として、未来にいた場所にジャンプします。
#### `Alt + →`

### 11. 呼び出し元を検索
フォーカス中のクラスやメソッドが呼び出されている箇所を検索します。
![呼び出し元検索](/image/コーディングを倍速にする/search_caller.png)
#### `Ctrl + Alt + H`
検索結果から選択することでもびだし元に移動もできます。

### 12. シグネチャを確認
フォーカス中のクラスやメソッド、変数の情報を確認します。
#### `F2`

### 13. ファイル検索
ワークスペース内のファイルを検索します。
#### `Ctrl + Shift + R`
![ファイル検索](/image/コーディングを倍速にする/search_resource.png)

### 14. クラス検索
プロジェクト内のクラスを検索します。
#### `Ctrl + Shift + T`
![クラス検索](/image/コーディングを倍速にする/search_class.png)
ファイル検索との違いは、クラス検索はクラスファイルも検索対象になる点です。
これにより、jarなどのライブラリの検索も行えます。

### 15. コメントアウト
フォーカス行をコメントアウトします。
`Ctrl + /`

### 16. Javaドキュメントを作成
複数行や見出しに使用するコメントアウトを作成します。
`/** + Enter`
![JavaDoc作成](/image/コーディングを倍速にする/create_javaDoc.png)
`Alt + Shift + J`でも作成できますが、Eclipseに限り可能な操作のようです。

### 17. 行削除
フォーカス行を削除します
`Ctrl + D`

### 18. ヒントを表示
エラーや警告が出ている行に対して、解決のヒントを表示します。
`Ctrl + 1`
![ヒント](/image/コーディングを倍速にする/view_hint.png)

### 19. ブレークポイントを配置
デバッグで処理を停止させるブレークポイントを配置します
`Ctrl + shift + B`

### 20. プロジェクトの更新
プロジェクトのファイルを再読み込みし、最新化します。
`F5`

### 21. ビルド
プロジェクトをビルド(コンパイル)します
`Ctrl + B`

