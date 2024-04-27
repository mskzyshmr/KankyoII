# Numpy
## 1 数学定数や初等関数
### 1.1 数学定数: pi, e  
```
import numpy as np # モジュールnumpyをnpとして使うことを宣言
print(np.pi)  
print(np.e)  
```

### 1.2 三角関数: sin, cos, tan
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

## 2 配列 (ndarray)
### 2.1 配列の作成
```
# 1次元配列の作成
x = np.array([1,2,3])

# 2次元配列の作成
x = np.array([[1,2,3],[4,5,6]])

# 3次元配列の作成
x = np.array([[[1,2,3],[4,5,6]],[[7,8,9],[10,11,12]]])
```

- 1次元配列（要素数N）  
    a[0], a[1], …, a[N-1]
- 2次元配列  
    a[0,0], a[0,1], a[0,2],…  
    a[1,0], a[1,1], a[1,2],…  
    a[2,0], a[2,1], a[3,2],…
- 3次元配列  
    a[0,0,0], a[0,0,1], a[0,0,2],…

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
作成：x = np.array([[1,2,3],[4,5,6]])  
要素の表示：print(x)

#### 自習  
- np.empty()  
- np.zeros()  
- np.ones()  
- np.eye()
- np.identity()

### 2.2 便利な関数：np.arange, np.linspace
- np.arange(stop)
- np.arange(start, stop[, step])

- np.linspace(start, stop, num)

### 2.3 配列の型
- int32：32ビット整数型
- int64：64ビット整数型
- float32: 32ビット浮動小数点数型
- float64：64ビット浮動小数点数型
> [!NOTE]
> これ以外にもあり

### 3 代入（アドバンスト）
#### 3.1 参照渡し: 配列（箱）の場所（アドレス）を代入
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

#### 3.2 値を代入: 配列（箱）の中身（値）を代入
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
