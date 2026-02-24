Chapter 1　イントロダクション
Chapter 2　JavaScript開発の基礎
Chapter 3　変数とデータ型
Chapter 4　演算子
Chapter 5　制御構文
Chapter 6　関数
Chapter 7　スコープ
Chapter 8　thisキーワード
Chapter 9　クラス
Chapter 10　組み込みオブジェクト
Chapter 11　コレクション
Chapter 12　反復処理
Chapter 13　非同期処理
Chapter 14　DOM
Chapter 15　イベント
Chapter 16　モジュール
Chapter 17　Node.js

---













<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
【参考】
🎯 まずは最小構成（ESLint + Prettier）
```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:prettier/recommended"
  ],
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "rules": {
    "no-unused-vars": "warn",
    "no-undef": "error"
  }
}
```

🎯 定数名の命名規則を強制する設定（重要）
✔ 通常の const → lowerCamelCase
✔ 不変の定数 → UPPER_SNAKE_CASE
を ESLint で強制するには id-match を使います。
```json
{
  "rules": {
    "id-match": [
      "error",
      "^[a-z][a-zA-Z0-9]*$|^[A-Z0-9_]+$",
      {
        "onlyDeclarations": true
      }
    ]
  }
}
```
このルールの意味
- userName → OK
- maxItems → OK
- API_BASE_URL → OK
- DEFAULT_TIMEOUT → OK
- UserName（先頭大文字）→ NG
- apiBaseUrl（不変値なのに camelCase）→ NG
→ チーム全体で命名規則がブレなくなる

🎯 さらに実務でよく使うルールセット
あなたの開発スタイル（保守性・可読性重視）に合う構成をまとめるとこうなります。
```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:prettier/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["@typescript-eslint"],
  "rules": {
    "@typescript-eslint/no-unused-vars": "warn",
    "@typescript-eslint/no-explicit-any": "warn",
    "no-console": "warn",
    "eqeqeq": ["error", "always"],
    "id-match": [
      "error",
      "^[a-z][a-zA-Z0-9]*$|^[A-Z0-9_]+$",
      { "onlyDeclarations": true }
    ]
  }
}
```
🧭 まとめ
- 定数名は小文字が一般的ではなく、用途で使い分けるのが正解
- ESLint の id-match を使えば命名規則を強制できる
- TypeScript + Prettier の構成が現代の標準
- あなたの開発スタイルなら「保守性重視のルールセット」が最適



🎯 まとめ（迷ったらこれ）
|  |  | 
|  |  | 
|  |  | 
|  |  | 
|  |  | 
|  |  | 
|  |  | 




