# ベースイメージ
FROM ubuntu:22.04

# 対話形式のプロンプトを無効化
ENV DEBIAN_FRONTEND=noninteractive

# Python3, pip, gitなどをインストール
RUN apt-get update && apt-get install -y \
    python3.10 \
    python3-pip \
    git \
    # 不要なキャッシュを削除
    && rm -rf /var/lib/apt/lists/*

# Ultralyticsライブラリをインストール (PyTorchなども自動で入ります)
RUN pip3 install ultralytics

# 実行スクリプトをコンテナにコピー
# (hogehoge_full.sh または hogehoge_low.sh がコピーされる)
COPY low-power/hogehoge.sh /hogehoge.sh
RUN chmod +x /hogehoge.sh

# コンテナ起動時にスクリプトを実行
CMD ["/hogehoge.sh"]
