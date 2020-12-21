# Quantum Playground

量子アニーリングシミュレータがあったからそれで遊ぶ。名前はBlueqat

## Blueqat

Install

`$ pip3 install blueqat`


## Docker

Jupyter環境がおかしいので、Dockerを立ててみようか。
[https://qiita.com/fuku_tech/items/6752b00770552bf4f46b](https://qiita.com/fuku_tech/items/6752b00770552bf4f46b)

```
`$ docker pull jupyter/scipy-notebook`
```
jupyterというコンテナ名を付けて8888番ポートでコンテナを作成＆起動
```
$ cd {here}
$ docker run -v `pwd`:/home/jovyan/work -p 8888:8888 --name jupyter jupyter/scipy-notebook
```

2回目以降

```
# コンテナ起動
$ docker start jupyter
　jupyter

# 状態を確認、STATUS: UPなら起動成功
$ docker ps

# もしトークンを確認された場合はコンテナに入ってログを出力する
$ docker exec -it jupyter bash
$ jupyter notebook list
　Currently running servers:
　http://localhost:8888/?token=<トークン>
```

停止したいとき
```
$ docker stop jupyter
```
