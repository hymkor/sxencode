v0.2.1
------
Jul 24, 2025

- Symbol can now be decoded into a string variable.

v0.2.0
------
Jul 23, 2025

- Made the delimiters for slices configurable via VectorOpen and VectorClose. The default was changed from `#(` and `)` to `(` and `)`.
- Implemented the `noname` tag option, which serializes the field as a standalone value instead of a `(name value)` pair.
- Removed the `(struct NAME)` format for struct names, as it was ultimately unused during decoding.
- Removed the `Name` type.
- Struct fields can now be decoded from both `(SYMBOL value)` and `("STRING" value)` forms.

v0.1.0
-------
Jul 23, 2025

- Implement `Decoder` and `Unmarshal`

v0.0.3
------
Jul 21, 2025

- Added support for struct tags `sxpr:"NAME,omitempty"` and `sxpr:",omitempty"` to omit fields with zero values from the S-expression output.
- Added support for `sxpr:"-"` struct tags to exclude fields from S-expression output entirely.
- Added support for a field of type ``sxencode.Name `sxpr:"SYMBOL"` `` in a struct to specify the symbol used in the struct header `(struct SYMBOL)`, similar to how "encoding/xml" works.
- Changed slice output to use the Lisp vector literal syntax `#(....)`.
- Removed the `ArrayHeader` and `ArrayIndex` fields from `Encoder`.
- Added support for calling the function set in `OnTypeNotSupported` when a type is not supported.
- For maps and structs, keys or field names are now omitted when their corresponding S-expression values are absent.
- For slices, if an element's S-expression is absent, `nil` is emitted instead.
- Added support for the struct tag `sxpr:"NAME"` to override the field name in S-expression output

v0.0.2
------

- Only `"` and `\` are escaped in string literals; other control characters (such as \n, \t, \r, etc.) are now output as raw characters
- Changed the package URL from `github.com/hymkor/sxencode` to `github.com/hymkor/sxencode-go`
- Changed struct type notation from `(struct-name NAME)` to `(struct NAME)`
- Modified `(*Encoder) Encode` to use the result of the `Sexpression() string` method, if implemented by an element in the input data
- Implemented the `Marshal` function

v0.0.1
------

- First release
