# addness-knowledge

Addnessプロダクトのナレッジベース。Cursorに突っ込むと、AIがAddnessの全機能を理解した状態で使える。

## セットアップ（初回のみ）

### 方法1: プロジェクトに直接クローン（推奨）

Addness関連のプロジェクトのルートで:

```bash
# リポをクローン
git clone https://github.com/kurosaki-yuto/addness-knowledge.git

# .cursor/rules にルールファイルをコピー
mkdir -p .cursor/rules
cp addness-knowledge/.cursor/rules/addness-product.mdc .cursor/rules/

# 詳細ドキュメントもプロジェクトに置く（任意）
cp -r addness-knowledge/docs ./docs/addness-knowledge
```

### 方法2: グローバルに使う

どのプロジェクトでも使いたい場合:

```bash
# ホームディレクトリにクローン
cd ~
git clone https://github.com/kurosaki-yuto/addness-knowledge.git

# Cursorの設定で「Rules」にこのファイルのパスを追加
# Settings > Rules > Add Rule > ~/addness-knowledge/.cursor/rules/addness-product.mdc
```

## 更新方法

```bash
# 最新版を取得
cd addness-knowledge
git pull
```

ルールファイルをプロジェクトにコピーしている場合は、再度コピーする:
```bash
cp addness-knowledge/.cursor/rules/addness-product.mdc .cursor/rules/
```

## ファイル構成

```
addness-knowledge/
├── README.md                          # このファイル
├── .cursor/
│   └── rules/
│       └── addness-product.mdc        # Cursorルール（要約版、自動適用）
└── docs/
    └── addness-全機能ナレッジ.md        # 全機能の詳細ドキュメント
```

## ナレッジの更新・追記

1. このリポをクローン
2. `docs/addness-全機能ナレッジ.md` を編集
3. 必要に応じて `.cursor/rules/addness-product.mdc` も更新
4. コミット & プッシュ

```bash
git add -A && git commit -m "ナレッジ更新: XXXを追記" && git push
```

チームメンバーは `git pull` するだけで最新が手に入る。
