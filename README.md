# Computational Creativity Final Project
***- A Sentiment-Driven Co-Creative Music Generation System -***

Analyzes lyrics inputted by human using Huggingface Transformers, an emotion analysis library, and presents chord progressions appropriate to the emotion of the lyrics.

<img width="1277" alt="image" src="https://github.com/NorikaNarimatsu/CC_final/assets/77351189/22bcd37d-f689-4bb9-9d46-e99bbbe8cf5c">



# How to use
● Input the your own name song name in "song_name", which will be used to create appropriate directories in Google Colab.

```
song_name = "can_you_feel_the_love_tonight"
```

<img width="800" alt="image" src="https://github.com/NorikaNarimatsu/CC_final/assets/77351189/32e02de1-eabb-4a8a-bcc0-fbd4026941ed">

It will create the corresponding folder on Google Colab File Directories

● Entering `key` and `lyric` in the `text2chord("key", "lyric") ` 
Example Input
```
text2chord("D","愛を感じて")
text2chord("D","世界を包む　ハーモニー")
text2chord("D","命の歌よ")
text2chord("D","話したいけどどうすればいい")
text2chord("D","過去の真実ああだめだ")
text2chord("D","王はあなた")
```
Example Output
```
愛を感じて : Cm7 Bm7 Bbm7 Eb / 0.8613585233688354

世界を包む　ハーモニー : G/B C D G D/F# / 0.7437107563018799

命の歌よ : G# G G# G / 0.744433581829071

話したいけどどうすればいい : G C#m7-5 F# G C#m7-5 F# / 0.686124861240387

過去の真実ああだめだ : Fm G Cm Bbm Eb / 0.5220361351966858

王はあなた : G A D G A D / 0.9682599306106567
```

* Convert chord to MIDI file

* Conver MIDI file to WAV using FluidSynth and pydub

<img width="827" alt="image" src="https://github.com/NorikaNarimatsu/CC_final/assets/77351189/fcbab71a-7b5f-4dfd-a959-27c72d4ab23f">



# Features
* Text input allows composition without any musical knowledge
* Generated music can be retrieved as a MIDI file, allowing user to freely edit the final product themselves

# Requirement
* Transformers
* Google　Account to run Colaboratory Environment 

# Installation

pacakege

```
!pip install fugashi
!pip install ipadic
!pip install pretty_midi
!apt-get install fluidsynth
!wget "https://schristiancollins.com/generaluser.php?action=download&name=GeneralUserGSfMTV11.zip" -O soundfont.zip
!unzip soundfont.zip
```

# Usage

For reasons such as Transformer setup, the Google Colaboratory environment specification is strongly recommended.

Step 1: When using Google Colaboratory, you can basically run the cells in order from the top. All the user has to do is,
Put any song name into song_name.
```
song_name = "can_you_feel_the_love_tonight"
```
Step 2: Also, enter the following in `text2chord("key", "lyric")`.
```
* key is selected from C G D A E B F# C# F Bb Eb Ab Db Gb Cb

* For "lyric", you are recommended to enter the lyrics in Japanese. (Even if English is included, some kind of chord progression will be output.)
```
* To add more lyrics, copy text2chord("key", "lyric") and paste it anywhere you want to generate music.

# Reference

* https://ichi.pro/furosutosongu-ai-o-shiyoshite-shi-kara-ongaku-o-seiseisuru-109320446959370
* transformers:https://github.com/huggingface/transformers
* https://qiita.com/hnishi/items/0d32a778e375a99aff13
* https://www.ufret.jp/
* https://qiita.com/kinopee0120/items/7bbcda4afa7e501d6272
* https://qiita.com/a2kiti/items/c0fea6e415bf7d743e16
