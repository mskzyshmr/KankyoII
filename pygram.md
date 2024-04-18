# Python文法
## 第1回 初歩的なこと
### 1 書式
- 大文字と小文字は区別される
- プログラム実行の際に無視される記述をコメントという
- \#の後は，コメントとして扱われる
- """と"""で囲まれた行は，コメントとして扱われる
- 字下げ（インデント）が意味を持つ（4文字分下げるのが標準）
- シングルクオーテーション' 'とダブルクオーテーション" "は区別されない

### 2 データ型（data type）
#### 2.1 型の種類       
-  str: 文字列
-  integer: 整数
-  float: 浮動小数点数  
-  bool: 真偽値（True or False）
-  None: 特殊な型

#### 2.2 型の問い合わせ: type
例）  
```
type('3')
type("3")
type(3)
type(3.0)
```
> [!CAUTION]  
> print(1+1)とprint('1'+'1')は違う結果になる．  

#### 2.3 型の変換: str, int, float
- str(引数): 引数を文字列型に変換
- int(引数): 引数を整数型に変換
- float(引数): 引数を浮動小数点数型に変換

### 3 代入: =
右辺を左辺に代入する．  
例）
```
x = 'abc'  # 文字列abcをxに代入  
x = 3      # 整数3をxに代入  
x = 3.0   # 浮動小数点数3.0をxに代入  
```

### 4 入出力
#### 4.1 ディスプレイ出力: print
括弧の中身がディスプレイ（標準出力）に表示される．  
例）
```
print('Hello World!')  
```

#### 4.2 キーボード入力: input
キーボードから入力されたものを変数に代入する．  
例）
```
x = input('Type a sentence.')  
print(x)  
````
> [!CAUTION]  
> input関数によって読み込まれたものは文字列型になる．  

### 5 四則演算など: +, -, *, /, \%, **
 - 和 x+y: 整数型同士の結果は整数型，浮動小数点数型同士の結果は浮動小数点数型，整数型と浮動小数点数型は浮動小数点数型
- 差 x-y: 和と同様
- 積 x*y: 和と同様
- 除算 x/y: 不動小数点数型除算（6/4=1.5）
- 商 x//y: 整数型除算（6//4=1）
- 剰余 x%y: 整数を整数で割った余り
- べき乗 x**y: 和と同様

> [!NOTE]  
> 演算優先順位: 1)** 2) *, /, \% 3) +, -  

### 6 ライブラリ
- 標準ライブラリ: Pythonの公式モジュールの集合（mathなど）
- 外部ライブラリ: それ以外のモジュールの集合（numpy, matplotlib, pandas, scipy, sklearnなど）

> [!NOTE]  
> ライブラリの宣言  
> import ライブラリ名  
> import ライブラリ名 as 別名  
> from ライブラリ名 import 変数名or関数名  

### 7 数学定数や初等関数
#### 7.1 数学定数: pi, e
> \# ライブラリmathを使うことを宣言  
>  import math  
>  print(math.pi)  
>  print(math.e)  

#### 7.2 三角関数: sin, cos, tan
- mathを使う
> \# ライブラリmathを使うことを宣言  
> import math  
>  
> \# degree→radian  
> math.radians(引数)  
>  
> \# radian→degree  
> math.degrees(引数)  
>  
> \# sine  
> math.sin(引数)  
>  
> \# cosine  
> math.cos(引数)  
>  
> \# tangent  
> math.tan(引数)  

- numpyを使う
> \# ライブラリnumpyを使うことを宣言  
> import numpy as np  
>  
> \# degree→radian  
> np.deg2rad(引数)  
>  
> \# radian→degree  
> np.rad2deg(引数)  
>  
> \# sine  
> np.sin(引数)  
>  
> \# cosine  
> np.cos(引数)  
>  
> \# tangent  
> np.tan(引数)  

> [!NOTE]  
> 三角関数の引数の単位はラジアン  
> mathとnumpyでは引数の種類が異なる．  

## 第2回 反復処理と条件分岐
### 8 演算子
#### 8.1 便利な演算子
| 演算子 | 意味 | 例 |
| - | - | - |
| += | 左辺の変数の値に右辺の値を足して左辺の変数に代入 | x += 1はx = x + 1と同じ |
| -= | 左辺の変数の値から右辺の値を引いて左辺の変数に代入 |  |
| *= | 左辺の変数の値に右辺の値を掛けて左辺の変数に代入 |  |
| /= | 左辺の変数の値を右辺の値で割って左辺の変数に代入 |  |

#### 8.2 比較演算子
| 演算子 | 意味 |
| - | - |
| == | 左辺は右辺と等しい |
| != | 左辺は右辺と等しくない |
| > | 左辺は右辺より大きい |
| < | 左辺は右辺より小さい |
| >= | 左辺は右辺より大きいか等しい |
| <= | 左辺は右辺より小さいか等しい |

#### 8.3 論理演算子
| 演算子 | 意味 |
| - | - |
| not | でなければ |
| and | かつ |
| or | または |

#### 8.4 便利な関数: range
- range(stop)
- range(start, stop[, step])

例）
```
print(list(range(3)))
[0, 1, 2] 
```
```
print(list(range(10)))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
```
print(tuple(range(3)))
(0, 1, 2)
```
```
print(tuple(range(10)))
(0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
```

#### 自習: 次の2つについて調べてみよう
- np.linspace
- np.arange

### 9 繰り返し: for, while
#### 9.1 for
```
for 変数 in range(N):
    N回繰り返される処理
```
> [!IMPORTANT]
> 字下げによってブロックを指定

```
for count in range(3):
    print(count)
```

#### 9.2 while
```
while 条件式:
    条件が真の場合の処理
```
> [!IMPORTANT]
> 字下げによってブロックを指定

```
count = 0
while count < 3:
    print(count)
    count += 1
```
> [!TIP]
> あらかじめ繰り返しの回数が決まっていない場合にwhileを用いることが多い

#### 自習: 次の3つについて調べてみよう
- len関数
- break文
- continue文

### 10 条件分岐: if
```
if 条件式:
    条件式が真の場合の処理（ifブロック）
```

```
if 条件式:
    条件式が真の場合の処理（ifブロック）
else:
    条件式が偽の場合の処理（elseブロック）
```

```
if 条件式1:
    条件式1が真の場合の処理
elif 条件式2:
    条件式1が偽で条件式2が真の場合の処理
else:
    上記の全て以外の場合の処理
```
> [!IMPORTANT]
> 字下げによってブロックを指定  
> ifブロックの中に，別のif文を使って入れ子にすることが可能  

#### 自習: 次の2つについて調べてみよう
- pass文
- in関数

## 第3回 配列と関数
### 11 配列
- 1次元配列（要素数N）  
    a[0], a[1], …, a[N-1]
- 2次元配列  
    a[0,0], a[0,1], a[0,2],…  
    a[1,0], a[1,1], a[1,2],…  
    a[2,0], a[2,1], a[3,2],…
- 3次元配列  
    a[0,0,0], a[0,0,1], a[0,0,2],…

#### 11.1 Numpyにおける配列の作成
例）
- 1行3列の整数型の配列  
作成：x = np.array([1,2,3])  
要素の表示：print(x)  
特定要素の抽出：print(x[1])  
型の表示：print(x.dtype)

- 1行3列の不動小数点型の配列  
作成：x = np.array([1.0,2.0,3.0])  
要素の表示：print(x)  
特定要素の抽出：print(x[1])  
型の表示：print(x.dtype)
	
- 2行3列の整数型の配列  
作成：y = np.array([[1,2,3],[4,5,6]])  
要素の表示：print(y)

#### 11.2 配列の型
- int32：32ビット整数型
- int64：64ビット整数型
- float32: 32ビット浮動小数点数型
- float64：64ビット浮動小数点数型
> [!NOTE]
> これ以外にもあり

### 12 関数
Pythonにはあらかじめ準備されている組み込み関数(type, str, int, float, print, input, range, ...)とユーザーが自由に定義できるユーザー定義関数がある．

#### 12.1 戻り値なしの関数
```
def 関数名(引数1, 引数2, …):
    処理
```

例）
```
def hello():
    print(‘Hello World!’)
hello()
```

#### 12.1 戻り値ありの関数
```
def 関数名(引数1, 引数2, …:
    処理
    return 戻り値
```

例1）
```
def plus(x, y):
    return x+y

z = plus(5,3)
print(z)
```

例2）
```
def plus_minus(x, y):
    return x+y, x-y

z1, z2 = plus_minus(5,3)
print(z1)
print(z2)
```

### 13 代入（アドバンスト）
#### 13.1 参照渡し: 配列（箱）の場所（アドレス）を代入
例）
```
import numpy as np
x = np.zeros(3)
print(x)
y = x
print(x, y)
y[1] = 1
print(x, y)
```

#### 13.2 値を代入: 配列（箱）の中身（値）を代入
例1）
```
import numpy as np
x = np.zeros(3)
print(x)
y = np.copy(x)
print(x, y)
y[1] = 1
print(x, y)
```

例2）
```
import numpy as np
x = np.zeros(3)
y = np.zeros(3)
y[:] = x[:]
print(x, y)
y[1] = 1
print(x, y)
```
