## 概要
このリポジトリには，ロボットを強化学習させたいときに．簡単にmujocoとGymnasiumを用いた環境を用意することができるテンプレートを用意している．

## Mujoco Gymnasium template
- 強化学習分野でデファクトスタンダードになりつつあるシミュレータMujocoとOpenAI Gymの後継にあたるGymnasiumを用いたテンプレート
- 学習部分を入れ替えると好きなライブラリや自作した学習器で学習させることが可能になる．

## ロボットモデルの定義について
以下のQiitaの記事を参考にされたい．
- [【Python】物理エンジンMuJoCoの紹介＆MJCFドキュメント【MuJoCoチュートリアル①】](https://qiita.com/Yayoi-Habami/items/1bf5a3e05b1516a90381#site%E3%81%AB%E3%81%AE%E3%81%BF%E6%8E%A5%E7%B6%9A%E5%8F%AF%E8%83%BD%E3%81%AA%E3%82%BB%E3%83%B3%E3%82%B5)
- [【Python】MuJoCo/actuatorドキュメント【MuJoCoチュートリアル②】](https://qiita.com/Yayoi-Habami/items/90f42ea10a32eb20fde8#motor-mjcfactuator-)

## 環境構築
1. 仮想環境の構築
好きなところに仮想環境を作る．（大抵はプロジェクトのルートディレクトリに作る）（anacondaでもOK）
```
python -m venv 仮想環境名
```

2. 必要なライブラリインストール
```
pip install gymnasium[mujoco]
```

## 通知bot
学習は，3時間とか6時間とかかかるものなので，終わったら通知が来ると嬉しい．そのため，LINE Notifyとslack APIを利用したbotを用意している．
LINE Notifyの方がTOKENを得るのが楽でおすすめ  
bot_setting.josnの例を示めす．[JSON の操作](https://developer.mozilla.org/ja/docs/Learn/JavaScript/Objects/JSON)を参考に，自身の環境に合わせて設定すると良い．

```
{
    "LINE_token":{

        "my_token":"*******************************************",
        },
    "slack_token":{
        "ws_token":"********************************************************"
    },
    "slack_ch":{
        "ws_ch":"general"
    }
}
```
参考

- [LINE NotifyのTOKEN取得方法](https://qiita.com/nattyan_tv/items/33ac7a7269fe12e49198)
- [Slack APIのTOKEN取得方法](https://note.com/npaka/n/n4bcb38a1ea74)
