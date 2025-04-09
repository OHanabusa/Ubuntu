✅ UbuntuにMinicondaをインストールする手順
🔹 Step 1: Minicondaのインストーラをダウンロード
bash
コピーする
編集する
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
※ARMアーキテクチャ（例: Raspberry Pi）の場合は別URLになるので要確認。

🔹 Step 2: インストーラを実行
bash
コピーする
編集する
bash Miniconda3-latest-Linux-x86_64.sh
プロンプトに従って進めてください：

ライセンス条項 → Enter を押し続けて進む

「同意しますか？」→ yes

インストール先のパス（デフォルトは ~/miniconda3 でOK）

🔹 Step 3: インストール後、condaを有効化
bash
コピーする
編集する
source ~/miniconda3/bin/activate
または一度ログアウト＆再ログインすると、.bashrc に追加された初期化スクリプトが反映されます。

🔹 Step 4: conda コマンドの確認＆更新
bash
コピーする
編集する
conda --version  # 最新の4.xになっているか確認
conda update -n base -c defaults conda
🔹 Step 5: FEniCS用の仮想環境を作成
bash
コピーする
編集する
conda create -n fenics -c conda-forge fenics
conda activate fenics
✅ 動作確認（PythonでFEniCS）
bash
コピーする
編集する
python -c "from dolfin import *; print('FEniCS is ready!')"
