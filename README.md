# bluebridge_preparation
## Numpy

```python
# 指定 1 维数组的数值类型为float64
a = np.array([1.1, 2.2, 3.3], dtype=np.float64) 
# 查看 a 及 dtype 类型
a, a.dtype
# 将 a 的数值类型从 float64 转换为 int，并查看 dtype 类型
a.astype(int).dtype  
# numpy.array 将列表或元组转换为 ndarray 数组
numpy.array(object, dtype=None, copy=True, order=None, subok=False, ndmin=0)
# 在给定区间内创建一系列均匀间隔的值
numpy.arange(start, stop, step, dtype=None)
# 在指定的区间内返回间隔均匀的值
numpy.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None)
# 快速创建数值全部为 1 的多维数组
numpy.ones(shape, dtype=None, order='C')
# 快速创建数值全部为 0 的多维数组
numpy.zeros(shape, dtype=None, order='C')
# 创建一个二维数组，其特点是 k 对角线上的值为 1，其余值全部为 0
numpy.eye(N, M=None, k=0, dtype=<type 'float'>)
# 将缓冲区转换为 1 维数组
numpy.frombuffer（buffer）
# 从文本或二进制文件中构建多维数组
numpy.fromfile(file，dtype，count，sep)
# 通过函数返回值来创建多维数组
numpy.fromfunction（function，shape）
# 从可迭代对象创建 1 维数组
numpy.fromiter（iterable，dtype，count）
# 从字符串中创建 1 维数组
numpy.fromstring（string，dtype，count，sep）
# 在不改变数组数据的同时，改变数组的形状
numpy.reshape(a, newshape)
# 将任意形状的数组扁平化
numpy.ravel(a, order='C')
# 将数组的轴移动到新的位置 
numpy.moveaxis(a, source, destination)
# 交换数组的轴
numpy.swapaxes(a, axis1, axis2)
# 类似于矩阵的转置，它可以将 2 维数组的横轴和纵轴交换
numpy.transpose(a, axes=None)
# 将输入数据直接视为 x 维
numpy.atleast_1d()
numpy.atleast_2d()
numpy.atleast_3d()
# 将特定输入转换为数组
asarray(a，dtype，order)
# 将多个数组沿指定轴连接在一起
numpy.concatenate((a1, a2, ...), axis=0)
# 沿着新轴连接数组的序列
numpy.stack(arrays，axis)
# split 及与之相似的一系列方法主要是用于数组的拆分
numpy.split(ary，indices_or_sections，axis)
# 沿特定轴删除数组中的子数组
numpy.delete(arr，obj，axis)
# 依据索引在特定轴之前插入值
numpy.insert(arr，obj，values，axis)
# 将值附加到数组的末尾，并返回 1 维数组
numpy.append(arr，values，axis)
# 对数组尺寸进行重新设定
numpy.resize(a，new_shape)
# 指定一个数组，并使用 [0, 1) 区间随机数据填充，这些数据均匀分布
numpy.random.rand(d0, d1, ..., dn)
# 前者是从标准正态分布中返回一个或多个样本值
numpy.random.randn(d0, d1, ..., dn) 
# 生成 [low, high) 的随机整数。注意这是一个半开半闭区间
numpy.random.randint(low, high, size, dtype)
# 会在 [0, 1) 区间内生成指定 size 的随机浮点数
numpy.random.random_sample(size) 
# 会给定的数组里随机抽取几个值，该方法类似于随机抽样
numpy.random.choice(a, size, replace, p) 
```

## Pandas

```python
# Series 是 Pandas 中最基本的一维数组形式。其可以储存整数、浮点数、字符串等类型的数据
pandas.Series(data=None, index=None, dtype=None, name=None, copy=False, fastpath=False)
# DataFrame 是 Pandas 中最基本的二维数据结构。其可以储存整数、浮点数、字符串等类型的数据
pandas.DataFrame(data=None, index=None, columns=None, dtype=None, copy=False)
# 读取 CSV 文件
pandas.read_csv("https://labfile.oss.aliyuncs.com/courses/906/los_census.csv")
# 转化为NumPy数组
df.values
# 可以基于数字索引对数据集进行选择。这里用到的 Pandas 中的 .iloc 方法。该方法可以接受的类型有：
# 整数。例如：5
# 整数构成的列表或数组。例如：[1, 2, 3]
# 布尔数组。
# 可返回索引值的函数或参数。
df.iloc[:, 1:4]
# 通过标签选择 df.loc[] 可以接受的类型有：
# 单个标签。例如：2 或 'a'，这里的 2 指的是标签而不是索引位置。
# 列表或数组包含的标签。例如：['A', 'B', 'C']。
# 切片对象。例如：'A':'E'，注意这里和上面切片的不同之处，首尾都包含在内。
# 布尔数组。
# 可返回标签的函数或参数。
df.loc[[0, 2], 'Median Age':]
# DataFrame.drop 可以直接去掉数据集中指定的列和行。
# 一般在使用时，我们指定 labels 标签参数，
# 然后再通过 axis 指定按列或按行删除即可
df.drop(labels=['Median Age', 'Total Males'], axis=1)
# DataFrame.drop_duplicates 可以去掉数据集中的重复行
DataFrame.drop_duplicates()
# DataFrame.dropna 可以去掉数据集中的缺失值
DataFrame.dropna(axis=0, how='any', thresh=None, subset=None, inplace=False)
# DataFrame.isna
DataFrame.isna()
# DataFrame.fillna 可以填充数据集中的缺失值
DataFrame.fillna(value=None, method=None, axis=None, inplace=False, limit=None, downcast=None)
DataFrame.fillna(df.mean()['C':'E'])
# 插值填充
DataFrame.interpolate(method='linear', axis=0, limit=None, inplace=False, limit_direction=None, limit_area=None, downcast=None)
```