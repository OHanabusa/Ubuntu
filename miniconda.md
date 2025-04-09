
# ✅ Ubuntuをインストールして，そこにMinicondaをインストールする手順

## 🔹 Step 1: Ubuntuをインストール
```
wsl --install
wsl
```

## 🔹 Step 2: Minicondaのインストーラをダウンロード

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

## 🔹 Step 3: インストーラを実行

```bash
bash Miniconda3-latest-Linux-x86_64.sh
```
プロンプトに従って進めてください：

- ライセンス条項 → Enter を押し続けて進む
- 「同意しますか？」→ `yes`
- インストール先のパス（デフォルトは `~/miniconda3` でOK）

## 🔹 Step 4: インストール後、condaを有効化

```bash
source ~/miniconda3/bin/activate
```
または一度ログアウト＆再ログインすると、`.bashrc`に追加された初期化スクリプトが反映されます。

## 🔹 Step 5: conda コマンドの確認＆更新

```bash
conda update -n base -c defaults conda
```

## 🔹 Step 6: (必要であれば)FEniCS用の仮想環境を作成

```bash
conda create -n fenics python=3.8 
conda activate fenics
conda install -c conda-forge fenics matplotlib meshio
```

## ✅ 動作確認（PythonでFEniCS）

```bash
python -c "from dolfin import *; print('FEniCS is ready!')"
```
## 補足
その他jupyter等が必要であれば，ChatGPT（ubuntuでjupyterのインストール）や検索して追加してください．
