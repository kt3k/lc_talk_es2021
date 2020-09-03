class: center, middle
# JavaScript の新機能 - 2021

日野澤 よしや

twitter.com/kt3k

---
class: center, middle

今日は JavaScript の新機能の話をします

---

自己紹介: 日野澤 歓也 (ひのさわ よしや)

<img src="assets/hino-marunouchi.jpg" width="250" >

- LC 技術アドバイザー 2019 -
- RLS フロントエンドテックリード 2015 - 2019
- GREE エンジニア 2012 - 2014

---

自己紹介: 日野澤 歓也 (ひのさわ よしや)

<img src="assets/hino-marunouchi.jpg" width="250" >

- フロントエンドが専門
- 普段は SEQSENSE という会社でフロントエンド開発をしています
- Deno という OSS のメンバー

---
class: center, middle

JavaScript の新機能の話

---
class: center, middle

JavaScript の新機能の決まり方
---
class: center, middle

JavaScript の仕様は<br/>ECMA International という団体が決めています。
---
class: center, middle

ECMA International の中でも特に<br />

TC39 とよばれる会議体が年6回開催されて、<br />その中で次の JavaScript への仕様提案がされ、<br />入れる入れないのジャッジが行われています。<br />
<br />

[tc39.es](https://tc39.es/) というサイトに詳細がまとまっています。

---
class: center, middle

今年は2月・3月・6月・7月に行われていて、<br />2月3月分は ES2020 で publish 済

---
class: center, middle

なので、今日は6月7月分の中からいくつかを紹介
---
# 4機能

- String.prototype.replaceAll
- Logical Assignment
- Numeric Separator
- Promise.any

---

# String.protoype.replaceAll

文字列を全部置き換えられます。

```
'aaa'.replaceAll('a', 'b') // => 'bbb'
```

今までも正規表現を使えば出来ました
```
'aaa'.replaceAll(/a/g, 'b') // => 'bbb'
```

---

# Logical Assignment

新しい代入文が増えます

```
a ||= b
```

↑これが、↓この意味になる

```
a = a || b
```

関数のパラメータに初期値を設定する時に使えそう! 💡

---

# Numeric Separator

```
const a = 1000000 // 100万
```

↑これが、こう書ける↓

```
const a = 1_000_000
```

3桁区切り的なものを入れて大きい数字を読みやすく書ける!

---

# Promise.any

```
await Promise.any([a, b, c])
```

↑ 上の a, b, c の中でどれか1つが resolve したら Promise.any() 全体が resolve になり、すべてが reject された場合に reject になる。

Promise.race はどれか1つが resolve or reject されたら全体が reject or reject になる、ので、微妙に違う

---

# 参考文献

- Babel チームが TC39 をウォッチするレポジトリ
  - https://github.com/babel/proposals
- TC39 公式アジェンダ
  - https://github.com/tc39/agendas
- TC39 公式議事録
  - https://github.com/tc39/notes

---
class: middle, center

ご清聴ありがとうございました! 🙇
