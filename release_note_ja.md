v0.2.1
------
Jul 24, 2025

- Symbol を文字列へ Decode できるようにした。

v0.2.0
------
Jul 23, 2025

- スライスの開始・終了に使う文字列を変数 `VectorOpen` , `VectorClose` で設定できるようにした。デフォルトを `#(` `)` から `(` `)` へ変更
- タグオプション `noname` を実装。これを指定したフィールドは `(名前 値)` ではなく、値単独でS式化されることを想定する
- 結局、Decode時には使わなかったので、構造体名を `(struct NAME)` 形式で出力するのをやめた
- `Name`型を削除
- `(SYMBOL value)` だけでなく `("STRING" value)` 形式も、構造体のフィールドとして Decode 出来るようにした

v0.1.0
-------
Jul 23, 2025

- 型`Decoder` と関数`Unmarshal` を実装

v0.0.3
------
Jul 21, 2025

- 構造体タグに `sxpr:"NAME,omitempty"` または `sxpr:",omitempty"` を指定することで、フィールドがゼロ値のときにそのS式出力を省略できるようにした
- 構造体タグに `sxpr:"-"` を指定することで、そのフィールドをS式出力から除外できるようにした
- 構造体に ``sxencode.Name `sxpr:"SYMBOL"` `` 型のフィールドを追加することで、構造体ヘッダ `(struct SYMBOL)` の SYMBOL を指定できるようにした（"encoding/xml" と同様）
- スライスの出力には、Lisp のベクタリテラル `#(....)` を用いるようにした
- `Encoder` からフィールド `ArrayHeader`, `ArrayIndex` を削除した
- 型がサポートされていない場合、OnTypeNotSupported に設定された関数を呼ぶようにした
- map,struct において、値のS式がない場合、キーやフィールド名も出力しないようにした
- スライスの要素において、値のS式がない場合、かわりに nil を出力するようにした
- 構造体のフィールドに `sxpr:"NAME"` タグを指定することで、フィールド名の代わりに NAME を S式出力に用いるようにした

v0.0.2
------
Jul 15, 2025

- 文字列中の `"` と `\` 以外の制御文字（例：`\n`, `\t`, `\r`, `\b`, `\a`）はエスケープせず、生の文字として出力するようにした
- パッケージの URL を `github.com/hymkor/sxencode` から `github.com/hymkor/sxencode-go` へ変更した
- `(struct-name NAME)` だった構造体の型名表記を `(struct NAME)` へ変更した
- `(*Encoder) Encode` に与えられたデータに含まれる要素に `Sexpression() string` というメソッドが実装されていた時、その要素のS式化にはそのメソッドの結果を利用するようにした。
- `Marshal` 関数を実装

v0.0.1
------
Jul 13, 2025

- 公開
