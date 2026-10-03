# 概要
- このプロジェクトでは、OpenAI o1 proが出力した登場人物の設定、鑑賞者の体験するカタルシスのタイプ、プロットタイプの分類データからデータベースを作り、ランダムに取り出して物語の設定資料のアイデアを作ります。
- このプロジェクトは、ChatGPT Proで使用できる、OpenAIのo1 pro modeの検証を兼ねています

# 手順
- ChatGPT Proのo1 pro modeに、物語のキャラクタータイプを生成させます
  - [character-type-protagonist-1.md](https://github.com/masa-jp-art/character-type-db/blob/main/character-type-protagonist-1.md)
  - [character-type-protagonist-2.md](https://github.com/masa-jp-art/character-type-db/blob/main/character-type-protagonist-2.md)
  - [Character-type-SubCharacter.md](https://github.com/masa-jp-art/character-type-db/blob/main/Character-type-SubCharacter.md)
  - [Character-type-antagonist.md](https://github.com/masa-jp-art/character-type-db/blob/main/Character-type-antagonist.md)
- ChatGPT Proのo1 pro modeに、「鑑賞者が体験するカタルシス」を分類させます
  - [catharsis-type.md](https://github.com/masa-jp-art/catharsis-type-db/blob/main/catharsis-type.md)
- ChatGPT Proのo1 pro modeに、物語のプロットを分類させます
  - [prot-type.md](https://github.com/masa-jp-art/prot-type-db/blob/main/prot-type.md)
- 出力された分類をスプレッドシートに転記してデータベースを作ります
  - [20250104-synopsis-list-snapshot](https://docs.google.com/spreadsheets/d/1qx4aUV2JA5RszAm4ghgAnzcDY3JY6dv5f7dpCJJ2lD8/edit)
- Google colabでプログラムを動かし、物語の設定を出力させます
  - https://github.com/masa-jp-art/synopsis-list-db/blob/main/cord-for-google-colab.py
 
# 関連
- [OpenAI o1 pro mode検証：o1 proが出力したアイデアを組み合わせて小説やシナリオを出力させられるか](https://note.com/msfmnkns/n/nc2e69de0ca26)

## 用語と組み合わせ例

このプロジェクトの「シノプシス用資料」は、完成した本文ではなく、登場人物・鑑賞者に届けたい感情（カタルシス）・出来事の型（プロット）をまとめた設定の入力素材です。たとえば説明用の架空例では、「記憶を探す主人公」「旅（クエスト）の型」「融和・和解のカタルシス」を組み合わせ、旅の目的と和解がどう結び付くかを検討できます。この例は実際の無作為抽出結果ではありません。

## 背景と系譜

概要と手順にあるように、o1 pro modeで作成したキャラクター・カタルシス・プロットの分類を、別々の資料から一緒に取り出す実験へ展開したものです。分類は創作の発想を増やすための生成AI由来の資料で、標準化された物語理論や心理学の分類として保証するものではありません。

## 技術的な流れと展開

[Colab用コード](cord-for-google-colab.py)は、Google Sheetsの `protagonist`、`SubCharacter`、`antagonist`、`catharsis`、`prot` の5シートから、それぞれ2列目の見出しを除いて1件をランダムに選び、設定資料として標準出力に表示します。現コードには、小説本文を生成するモデルへの呼び出しはありません。

出力された資料を見比べて採用する組み合わせを選び、人の執筆や別の生成工程への入力として使えます。シートの準備・Google認証は必要で、生成された分類どうしの整合性や物語としての採用判断は利用者が確認します。

