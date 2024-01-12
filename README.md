# Computational Creativity Final Project
***- A Sentiment-Driven Co-Creative Music Generation System -***

Analyzes lyrics inputted by human using Huggingface Transformers, an emotion analysis library, and presents chord progressions appropriate to the emotion of the lyrics.

# How to use
● Input the your own name song name in "song_name", which will be used to create appropriate directories in Google Colab.

```
song_name = "can_you_feel_the_love_tonight"
```
● Entering `key` and `lyric` in the `text2chord("key", "lyric") ` 
```
text2chord("D","愛を感じて")
text2chord("D","世界を包む　ハーモニー")
text2chord("D","命の歌よ")
text2chord("D","話したいけどどうすればいい")
text2chord("D","過去の真実ああだめだ")
text2chord("D","王はあなた")
```

```
la3 : G F# Bm
人は何度見上げれば空が見えるのか : Emaj7 Em7 Emaj7 Em7
人にはいくつ耳があれば人々の悲しみが聞こえるのか : G F#7 Bm Am D
どれ位の人が死んだら : Dmaj7 A/C# Bm Dm
あまりにも多くの人が亡くなったことに気づくのか : G A D G A D
友よ答えは風に吹かれて : G#/C A#m G# G#/C A#m G#
風に吹かれている : Bm F#/Bb Bm F#/Bb
la3 : G F# Bm
```

* 「Magentaでメロディを生成」の実行で、音楽を生成

* 「生成音楽の再生」の実行で、生成された音楽を確認

* 生成された音楽をMIDIファイルとしてダウンロードし、DAWソフトなどで自由に編集することも可能

<img width="562" alt="スクリーンショット 2022-05-19 12 28 48" src="https://user-images.githubusercontent.com/105255463/169198255-5777751e-430c-4701-ac2e-c877a9884f8e.png">



# Features

* テキスト入力により、音楽の知識がなくても作曲が可能
* 歌詞ごとにMIDIファイルを作成しているため、magentaよりも自由なコード進行が可能
* 音楽学習生成ライブラリMagentaで学習させたモデルを用いているため、別途自分で学習させたモデルを使用することで自分好みの音楽を生成させることが可能
* 生成された音楽はMIDIファイルとして取得することができるため、最終的に自分で自由に編集が可能

# Requirement

* Magenta
* Transformers
* その他

# Installation

パッケージのインストール

```
!git clone https://github.com/noriakihanya/EmotionsMelody.git
!pip install -r /content/EmotionsMelody/requirements.txt
!apt install fluidsynth
!cp /usr/share/sounds/sf2/FluidR3_GM.sf2 ./font.sf2
!pip install midi2audio
```

# Usage

Google Colaboratoryを使用する場合、基本的にセルを上から順番に実行することができるため「詩をコードに変換」セルの使い方について以下で説明

「詩をコードに変換」セルの`text_to_chord("key","lyric")`にそれぞれ以下のように入力する。

* keyはC G D A E B F# C# F Bb Eb Ab Db Gb Cb　から選択

* lyricは、基本的に歌詞を日本語で入力する。（英語が含まていても何かしらのコード進行は出力される。）

* "la+n"を入力することで、n個分のコード進行がランダムで表示される。現在１〜１０まで対応しているが、９は対象なし。なお、n個分のコード進行が得られないことがある（コードが１つや２つしか出力されない時がある）ため、任意のコード進行が得られるまで実行ボタンを押下して任意のコード数を得るは可能となっている。※対応方法については検討中

```
text_to_chord("D","la3")
```
```
la3 : G F# Bm
```

* 歌詞を増やす場合、text_to_chord("key","lyric")をコピーし、任意の箇所にペーストすることで好きな場所に音楽を生成させることができる。

# Reference

* magenta:https://github.com/magenta/magenta
* transformers:https://github.com/huggingface/transformers
