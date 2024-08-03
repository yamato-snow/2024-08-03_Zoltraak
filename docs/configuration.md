

## 用語定義（2024-08-03修正版）

| システム用語 | 魔法体系 | 説明 | 自然言語プログラミング体系 |
|---|---|---|---|
| インタプリタ実行 | 即時魔法 | 対話形式の自然言語による指示のこと。即座に魔法を発動できる。<br>※対話形式で自然言語による指示を即座に実行します。 | zoltraak 魔導書 |
| コンパイラ実行 | 錬成魔法 | ドキュメント形式で記述された魔法の定義のこと。じっくりと魔法を錬成できる。<br>※ドキュメント形式で記述された魔法（プログラム）を事前に変換し実行します。 | zoltraak 魔導書 --prompt 呪文 |
| コンパイラ | 錬成器、起動式 | 詠唱から魔導書、魔法陣を錬成するための道具のこと。 錬成機自体は起動式が記述されている。魔法の品質を高めるのに役立つ。<br>※魔法（プログラム）を変換するための道具です。品質向上に役立ちます。 | zoltraak -c 錬成器 |
| 自然言語プログラム | 魔導書、魔法式、術式 | 魔法の理論や使い方を体系的にまとめた書物のこと。魔法の学習に役立ちこれ自体は一般言語で執筆されている。zoltraakにより魔法を発動することも出来る。<br>※一般言語で書かれた魔法（プログラム）の理論や使用方法をまとめた文書です。 | zoltraak 魔導書 |
| 高級言語プログラム | 古代魔導書 | 太古の魔法使いたちが残した神秘的な書物。ルーン文字で書かれており、強力な魔法の秘密が記されている。解読は容易ではないが、魔法の真髄を学ぶことができる。<br>※解読が難しいが強力な魔法（プログラム）が記された神秘的な文書です。 | zoltraak -a 古代魔導書 |
| 機械語 | 魔法石 | 魔導書を錬成器で錬成したもの、魔導書を実行すると魔法石により魔法が発動する。<br>※魔導書を錬成器で変換したもので、実際に魔法（プログラム）を発動させます。 | zoltraak -c 魔法石.md |



### 文字
| システム用語 | 魔法体系 | 説明 |
|---|---|---|
| 自然言語 | 世界語 | 人間が日常的に使用する言語。自然に発生し、文法や語彙が複雑。魔法を唱えるのに使われる。<br>※日常的に使用される言語で、魔法（プログラム）の指示に使用されます。 |
| プログラミング言語 | 古代語 | 魔法を正確に記述するための言語。厳密な文法と限られた語彙を持つ。魔導書の記述に使われる。<br>※厳密な文法を持つ言語で、魔導書（プログラム）の記述に使用されます。 |

### 術式

| 術式 | 説明 |
|:--|:--|
| 起動術式 | 魔法術式を構築するための術式<br>※魔法術式（プログラム）を構築するための基本的な術式（コード）です。 |
| 魔法術式 | イメージを具体的に記した術式のこと<br>※具体的な魔法（プログラム）の内容を記述した術式（コード）です。|
| 魔法陣 | 魔法術式の中でも視覚情報は魔法陣と呼ぶ<br>※視覚的な情報を含む魔法術式（グラフィカルなインターフェース）です。|
| 領域術式 | 魔法術式を得て領域を具現化する術式<br>※魔法術式を用いて特定の領域（プログラムの実行環境）を具現化する術式です。 |
| 視覚術式 | 魔法術式を得て領域を具現化する術式、魔導書に相当する魔法術式は文字情報が多いため、視覚化する目的でも利用する<br>※魔法術式を視覚化するための術式で、複雑な情報の理解を助けます。 |


## 主な機能（予定）

1. 様々な高級言語のコードへの変換
   - 対応言語: Python, Java, C++, JavaScript, TypeScriptなど
   - 使用例: `zoltraak convert markdown.md --language python`

2. AIを活用したコード生成
   - AnthropicのClaude AIモデルを利用
   - 使用例: `zoltraak generate --prompt "ユーザー認証システムを作成"`

3. キャッシュによる高速再実行
   - 変換済みファイルをキャッシュし、再利用
   - 使用例: `zoltraak run cached_script.py`

4. 進捗追跡とテスト実行
   - プロジェクトの進捗状況を可視化
   - 自動テストケースの実行
   - 使用例: `zoltraak test project_directory`

5. CI/CDワークフロー統合
   - 継続的インテグレーション/デリバリーとの連携
   - 使用例: `zoltraak integrate --ci jenkins`



| |プロンプト|ドキュメント|高級言語|
|---|---|---|---|
|ファイルなし|zoltraak docs --prompt text<br>`zoltraak create --prompt "新規プロジェクト作成"`|zoltraak docs<br>`zoltraak create project.md`|zoltraak docs<br>`zoltraak create script.py`|
|ファイルあり (修正変更なし)|zoltraak docs --prompt text<br>`zoltraak run --prompt text.txt`|zoltraak docs<br>`zoltraak convert doc.md`|zoltraak docs<br>`zoltraak execute code.js`|
|ファイルあり (修正変更あり)|zoltraak docs --prompt text<br>`zoltraak update --prompt modified_text.txt`|zoltraak docs<br>`zoltraak update modified_doc.md`|zoltraak docs<br>`zoltraak update modified_code.cpp`|

各コマンドの説明：
- create: 新しいファイルやプロジェクトを作成します。
- run/execute: 既存のファイルを実行または処理します。
- update: 変更されたファイルを更新し、必要に応じて再処理します。

この表では、各セルに `zoltraak {ファイル名}` の形式でファイル名を入れています。

- 左側の列は、ファイルの有無とファイルの状態を表しています。
  1. ファイルなし
  2. ファイルあり (修正変更なし)
  3. ファイルあり (修正変更あり)

- 上側の行は、ファイルの種類とその説明を表しています。
  - テキストファイル (読み上げ文章)
  - マークダウンファイル (要件定義書)
  - Pythonファイル (高級言語)

各セルには、対応するファイルの種類に基づいて `zoltraak 読み上げ文章`、`zoltraak 要件定義書`、`zoltraak 高級言語` のようなコマンドが入っています

この表は、ファイルの有無とファイルの状態の関係性を明確に表現しており、ファイルの種類ごとにそれぞれの状態が適用可能であることを示しています。また、各セルにファイル名を入れることで、具体的なファイルの例を提供しています。


## オプション（Option）

Zoltraakには以下のようなオプションが用意されています。

- `--output-dir`: 
  - 生成されたPythonファイルの出力ディレクトリを指定します。
  - デフォルトは`generated`ディレクトリです。
  - 例: `zoltraak convert source.md --output-dir ./generated`

- `-p`, `--prompt`: 
  - 追加のプロンプト情報を指定します。
  - これにより、既存のMarkdownファイルに対して変更を提案したり、新しい要件定義書を生成することができます。
  - 例: `zoltraak update doc.md -p "セキュリティ機能を追加"`

- `-c`, `--compiler`: 
  - 要件定義書のテンプレートとなるMarkdownファイルのパスを指定します。
  - デフォルトは`reqdef.md`です。
  - 例: `zoltraak compile code.py -c custom_compiler.json`

これらのオプションを使うことで、Zoltraakの機能をより柔軟に活用できます。例えば、既存のMarkdownファイルに対して変更を提案したり、新しい要件定義書を生成することができます。

また、要件定義書のテンプレートとなるMarkdownファイルを変更することで、生成される要件定義書の形式を変更することも可能です。

オプションの組み合わせ例：
```
Copyzoltraak convert source.md --output-dir ./output --language python -p "データ処理機能を最適化" -c custom_settings.json
```
この例では、source.mdをPythonコードに変換し、カスタム設定を適用しながらデータ処理機能を最適化し、結果を./outputディレクトリに出力します。


## 様々なプログラミング言語でのZoltraakの利用方法（作成予定）

Zoltraakは多くのプログラミング言語に対応しています。以下に主要な言語での利用例を示します。

### Python
```bash
zoltraak create script.py -p "ユーザー情報を管理するクラスを作成"
zoltraak update utils.py -p "CSVファイル処理関数を最適化"
```
Pythonの特徴：動的型付け、豊富なライブラリ、データ科学での広い利用

### JavaScript
```bash
zoltraak create app.js -p "Reactでインタラクティブなコンポーネントを実装"
zoltraak update server.js -p "ExpressでRESTful APIを拡張"
```
JavaScriptの特徴：フロントエンド・バックエンド両方で使用可能、非同期処理

### Java
```bash
zoltraak create Main.java -p "学生成績管理システムのメインクラスを作成"
zoltraak update UserService.java -p "ユーザー認証機能を強化"
```
Javaの特徴：強力な型システム、大規模アプリケーションに適する、プラットフォーム独立性

### C++
```bash
zoltraak create main.cpp -p "効率的なデータ構造を実装"
zoltraak update algorithm.h -p "ソートアルゴリズムを最適化"
```
C++の特徴：高性能、低レベル操作可能、システムプログラミングに適する

### Ruby
```bash
zoltraak create app.rb -p "Webスクレイピング機能を実装"
zoltraak update api.rb -p "GraphQLエンドポイントを追加"
```
Rubyの特徴：読みやすい文法、Webアプリケーション開発での人気、メタプログラミング

各言語固有の機能や最適化については、Zoltraakが適切に対応します。例えば、Pythonではリスト内包表記を活用し、Javaでは適切なデザインパターンを適用するなど、言語の特性を活かしたコード生成を行います。