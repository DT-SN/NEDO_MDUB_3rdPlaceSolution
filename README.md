# NEDO Challenge, Motion Decoding Using Biosignals
This repository contains 3rd-place-solution for the [NEDO Challenge, Motion Decoding Using Biosignals](https://signate.jp/competitions/1430)

## ディレクトリ構成
```
├── input
│   ├── readme.md
│   ├── reference.mat
│   ├── sample_submit.json
│   ├── test.mat
│   └── train.mat
├── notebook
│   ├── NEDOG_postprocess.ipynb
│   ├── NEDOG_preprocess1.ipynb
│   ├── NEDOG_preprocess2.ipynb
│   ├── NEDOG_train_acc.ipynb
│   ├── NEDOG_train_vel_1c_p10.ipynb
│   ├── NEDOG_train_vel_1c_p15.ipynb
│   ├── NEDOG_train_vel_1c_p6.ipynb
│   ├── NEDOG_train_vel_fc_p10.ipynb
│   ├── NEDOG_train_vel_fc_p5.ipynb
│   ├── NEDOG_train_vel_fc_p6.ipynb
│   ├── NEDOG_train_vel.ipynb
│   ├── NEDOG_train_vel_stacking.ipynb
└── working
```

## ノートブック概要
| ファイル名                      | 概要                                                           |
| ------------------------------- | -------------------------------------------------------------- |
| NEDOG_preprocess1.ipynb         | matからDataFrameに変換し、xy軸補正                             |
| NEDOG_preprocess2.ipynb         | EMGデータの加工と目的変数の加工を行い、データ水増し            |
| NEDOG_train_acc.ipynb           | 加速度をLightGBMで学習/推論(Regressor Chainなし)               |
| NEDOG_train_vel.ipynb           | 速度をLightGBMで学習/推論(Regressor Chainなし)                 |
| NEDOG_train_vel_1c_p6.ipynb     | 速度をLightGBMで学習/推論(Regressor Chain 直前のみ  6周期単位) |
| NEDOG_train_vel_1c_p10.ipynb    | 速度をLightGBMで学習/推論(Regressor Chain 直前のみ 10周期単位) |
| NEDOG_train_vel_1c_p15.ipynb    | 速度をLightGBMで学習/推論(Regressor Chain 直前のみ 15周期単位) |
| NEDOG_train_vel_fc_p5.ipynb     | 速度をLightGBMで学習/推論(Regressor Chain 累積  5周期単位)     |
| NEDOG_train_vel_fc_p6.ipynb     | 速度をLightGBMで学習/推論(Regressor Chain 累積  6周期単位)     |
| NEDOG_train_vel_fc_p10.ipynb    | 速度をLightGBMで学習/推論(Regressor Chain 累積 10周期単位)     |
| NEDOG_train_vel_stacking.ipynb  | 速度をLightGBMで学習/推論(Stacking/Regressor Chainなし)        |
| NEDOG_postprocess.ipynb         | 後処理および提出ファイル作成                                   |

## 実行手順
1. 環境に合わせて各ノートブックのHOMEディレクトリ設定を修正
2. 下記ノートブックを上から順に実行
  - NEDOG_preprocess1.ipynb
  - NEDOG_preprocess2.ipynb
  - NEDOG_train_acc.ipynb
  - NEDOG_train_vel.ipynb
  - NEDOG_train_vel_1c_p6.ipynb
  - NEDOG_train_vel_1c_p10.ipynb
  - NEDOG_train_vel_1c_p15.ipynb
  - NEDOG_train_vel_fc_p5.ipynb
  - NEDOG_train_vel_fc_p6.ipynb
  - NEDOG_train_vel_fc_p10.ipynb
  - NEDOG_train_vel_stacking.ipynb
  - NEDOG_postprocess.ipynb
3. 全て実行するとworkingディレクトリ内にsubmission.jsonが生成される
