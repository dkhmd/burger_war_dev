# burger_war_docker
Ubuntu 18.04 + ROS melodic環境

---
# Ubuntu 18.04 LTS用

## step1. dockerをインストール

[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

```
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable test edge"
sudo apt-get update
sudo apt-get install -y docker-ce docker.io
```

- Macの場合は以下 <br>
[Macにdockerインストール](https://qiita.com/ama_keshi/items/b4c47a4aca5d48f2661c) <br>

## step2. コンテナ起動

作成中

```
sudo docker run -p 6081:80 --shm-size=512m seigott/burger_war_docker
```

## step3. 動作確認

コンテナ起動後、chrome等のブラウザに以下を入力してコンテナへアクセス

```
localhost:6081
```

アクセスできたら以下により動作検証する

左下アイコン --> system tools --> terminator

Terminalを2つ用意してそれぞれで以下を実行

```
cd ~/catkin_make/src/burger_war
bash scripts/sim_with_judge.sh
```

```
cd ~/catkin_make/src/burger_war
bash scripts/start.sh
```

---

開発用

## docker build

xxx is container version

```
docker build -t burger_war_docker:xxx .
```

## docker compose

```
docker-compose up -d
```