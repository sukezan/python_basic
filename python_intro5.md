#Pythonで複数行のコードを記述
##複雑なコードの書き方

###条件分岐(if...else, if...elif...else)
> もし...ならば~する。生きていく上でいくつかの判断は必要である。

条件分岐はプログラムを書く上で避けては通れない部分です。ある条件を与え、それをみたす場合のみコードを動かすことができます。以下の例を*Visual Studio Code*に記述してください。ファイル名は`switch_func.py`とします。

```
if 5 > 3:
	print('Fulfill conditions')
```
if文は`if 条件式:`で次の行はインデント(indent)してコードを書く。インデントとは字下げの意味でtabを使います。

```
$ python3 switch_func.py
Fulfill conditions
```
ターミナルで実行してみましょう。なぜ`'Fulfill conditions'`が実行されるのはif文の内容が`True`。条件が成り立ったのでコードが実行された。

`switch_func.py`を以下のように書き換えてください。

```
name = 'Python'
if name == 'Python':
	print('you can do programing easy')
else:
	print('you can do nothing')
```
`if...else`はもし...もしくはという意味。つまり条件を満たさない場合の処理を`else`以下のコードで実行される。

さらに条件を増やしたい場合は`elif`を使う。

```
your_language = 'English'
if your_language == 'Japanese':
	print('こんにちは')
elif your_language == 'English':
	print('Hello')
elif your_language == 'German':
	print('Hallo')
else:
	print('None')
```

それぞれ実行してみて動きを確認してみてください。

###ループ(Loop)
> 繰り返しでめんどくさい処理はコーンピュータに任せろ

####リストのループ
ループとは"輪"という意味。複数回の処理"輪"のように繰り返し行う必要がある場合、コードはできるだけ減らしたい。そんな時にこのループを使うと便利です。

```
countries = ['Japan', 'Korea', 'China']
for country in countries: #リストから要素を一個ずつ取り出して'country'に格納
     print(country)
```
ここで使っている`#`はコメントアウトと呼ばれるものです。これはコードではなくコメントだと明示しています。ではファイル名を`loop.py`にして実行してみましょう。

```
$ python3 loop.py
Japan
Korea
China
```
このようにリスト`countries`の前から順番に取り出して`country`に格納される。その格納された要素を順番に出力される。またリストの繰り返しは範囲指定ができます。

```
 for country in countries[1:3]:
    print(country)
```
これも実行してみましょう。

```
$ python3 loop.py
Korea
China
```
今回の場合はリストの1番目から2番目の要素のみを取り出しています。`[開始番号:終了番号の一つ後ろ]`で範囲指定します。
####タプルのループ
タプルの要素も繰り返し取り出しができます。

```
tuple = 32, 1, 'Python'
for value in tuple:
	print(value)
```
実行すると以下の通りになります。リストのループと同じです。

```
$ python3 loop.py 
32
1
Python
```

####辞書のループ
ちなみにリストだけではなく辞書もループで繰り返しすることができます。

```
dict = {'Name':'Python','Versions':3.9}
for key in dict:
    print(key)
```
```
$ python3 loop.py
Name
Versions
```
この場合辞書のキーの要素が取り出されます。バリューやキーとバリューの両方を取り出すには`.values()`と`.items()`で取り出せます。

```
dict = {'Name':'Python','Versions':3.9}
for value in dict.values():
    print(value)
```

```
dict = {'Name':'Python','Versions':3.9}
for key, value in dict.items():
    print(key)
    print(value)
```
これらのコードを書いて実際に実行して確認してください。

```
$ python3 loop.py
Python
3.9
```

```
$ python3 loop.py
Name
Python
Versions
3.9
```
こうなれば正解です。

###関数(Function)
> 値を与えると何かしらの値が返ってくるもの

####関数を呼び出す
関数は`def 関数名()`で定義することができます。関数を呼び出すには`関数名()`で呼び出すことができます。

```
def output():
	print('Hello Python')

output()
```
実際に実行してみましょう。ファイル名は`function.py`にしてください。

```
$ python3 function.py 
Hello Python
```

####引数
では関数に値を与えて呼び出してみましょう。与える値のことを引数と言います。

```
def output(name):
	print(name)

name = 'Python'
output(name)
```
`output()`という関数に`name`という引数を与えます。

```
$ python3 function.py
Python
```
今回は`'Python'`という文字列を関数の引数として関数が呼び出された。

####引数と戻り値
引数は関数に与える値、戻り値は呼び出し元に戻る値のことです。では実際に記述してみましょう。

```
def calc(num):
	add = num + 2 #引数と2を足し算
	
	return add
num = 2	
add = calc(num) #呼び出し元
print(add)
```

```
$ python3 function.py
4
```
`return`で値を呼び出し元に返すことができる。今回は引数が2で、その値に2を足して呼び出し元へ戻す。

###まとめ
- 条件分岐：`if...else, if...elif...else`
- ループ：`for ... in _:` `values()` `items()`
- 関数：`def ...():` `return`

お疲れ様でした。これで基礎的なPythonのチュートリアルは終わりました。もっと高度なことを学びたい場合は[Pythonチュートリアル](https://docs.python.org/ja/3/tutorial/)を参照するか、いろいろな本があるのでそれを読んで勉強してください。


<a href="python_intro4.html">前へ(スクリプトファイルから実行)</a>

<a href="python_intro.html">初めに戻る</a>