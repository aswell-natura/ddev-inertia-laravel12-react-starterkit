# 環境構成 / Environment Setup

* [日本語](#日本語)
* [English](#english)

---

## 日本語

### 目的

デプロイをスムーズに進めるため、以下の環境構成を採用します。

### 使用技術

* **Laravel 12**
  → Inertia 最新版 2.0 を利用するため
* **MySQL 8.4 (LTS)**
  → 安定版・バグ修正済み

### 必須インストール

* **WSL（推奨）**
  → Docker Desktop のパフォーマンス最適化
* **PHP 8.2**
  → Laravel 12 に対応
* **Docker Desktop**
* **DDEV**
  → Docker 環境の構築と実行を簡単にする
  ※ Docker Desktop との統合を選択
* **Node.js / npm**

---

### 初期セットアップ

#### ■ 新規作成する場合

1. Laravel プロジェクトを作成

   ```bash
   laravel new my-app
   ```
2. Starter Kit を選択（React / Vue / Livewire）
3. DDEV をセットアップ

   ```bash
   ddev config
   ```
4. `./.ddev/config.yaml` を開き、Docker 設定を必要に応じて変更
5. 下記の開発手順に進みます

#### ■ テンプレートを使う場合

以下のリポジトリを clone してください。

```bash
git clone https://github.com/aswell-natura/ddev-inertia-laravel12-react-starterkit.git
```

その後、以下を実行します。

```bash
ddev composer install
ddev php artisan key:generate
ddev php artisan migrate
ddev npm install
ddev npm run build
```

---

### 開発時

#### バックエンド / 全体起動

```bash
ddev start
```

→ 実行すると、自動的に `.env` ファイルが作成されます。

または

```bash
ddev launch
```

#### フロントエンド開発

```bash
ddev npm run dev
```

#### 実行中のサーバーを確認

```bash
ddev describe
```

#### ddev を停止

```bash
ddev stop --unlist <project_name>
```

#### ddev を再起動

```bash
ddev restart
```

---

## English

### Purpose

To ensure a smooth deployment process, we use the following environment setup.

### Tech Stack

* **Laravel 12**
  → Required to use Inertia.js v2 (latest)
* **MySQL 8.4 (LTS)**
  → Stable version with long-term support

### Required Installations

* **WSL (Recommended)**
  → Improves Docker Desktop performance
* **PHP 8.2**
  → Compatible with Laravel 12
* **Docker Desktop**
* **DDEV**
  → Simplifies Docker-based development
  ※ Choose Docker Desktop integration
* **Node.js / npm**

---

### Initial Setup

#### ■ Create a New Project

1. Create a Laravel project

   ```bash
   laravel new my-app
   ```
2. Select a Starter Kit (React / Vue / Livewire)
3. Set up DDEV

   ```bash
   ddev config
   ```
4. Open `./.ddev/config.yaml` and adjust Docker settings if needed
5. Continue to the development steps below

#### ■ Using the Template

Clone the following repository:

```bash
git clone https://github.com/aswell-natura/ddev-inertia-laravel12-react-starterkit.git
```

Then run:

```bash
ddev composer install
ddev php artisan key:generate
ddev php artisan migrate
ddev npm install
ddev npm run build
```

---

### Development

#### Start Backend / Full Stack

```bash
ddev start
```

→ This will automatically generate the `.env` file.

Or open the project in browser:

```bash
ddev launch
```

#### Frontend Development

```bash
ddev npm run dev
```

#### Check Running Servers

```bash
ddev describe
```

#### Stop ddev

```bash
ddev stop --unlist <project_name>
```

#### Restart ddev

```bash
ddev restart
```
