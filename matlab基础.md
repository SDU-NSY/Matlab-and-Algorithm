### matlab帮助的使用

- help + 函数名
- lookfor可以加缺省函数名
- doc + 函数名以超文本方式给出

### 数据的输入

##### 直接输入

- 一行的元素用逗号或空格分开
- 行之间用 ; 分开

##### 分行输入

```matlab
A = [1,2,3
	 4,5,6
	 7,8,9];
```

##### 特殊向量

- t = logspace(n1,n2,n) 在10^n1 到 10^n2之间按照对数距离等间距产生n个数  缺省n时产生50个数

##### 特殊矩阵

- 单位矩阵
  - eye(m,n) 得到最大单位矩阵，其余位置补0

- 空矩阵
  - 可以利用空矩阵删除矩阵的元素 eg：a(:,3) = [] ,删除矩阵a的第三列

- 随机数矩阵
  - ![image-20210730095856810](C:\Users\nishiyu\AppData\Roaming\Typora\typora-user-images\image-20210730095856810.png)

- 随机置换
  - ![image-20210730100051919](C:\Users\nishiyu\AppData\Roaming\Typora\typora-user-images\image-20210730100051919.png)

### 矩阵四则运算与矩阵函数运算

- num2str() 将矩阵转化为字符串
- isspace() 返回一个==逻辑数组== ，有空的地方为1，其它为0
- logical() 可以将double类型的数组修改为逻辑数组
- ==数组索引必须为正整数和逻辑值==
- `A(:)` 语法将 `A` 的元素转换成单列向量
- any(A) 判断每一列是否有非0值 ， any(A,2) 按行判断，返回==逻辑数组==

### 数值积分

##### 离散点的数值积分

- 已知一元函数的离散点观测值，求一重数值积分 trapz(x,y)

##### 函数的数值积分

已知被积函数表达式

- 一元 integral(fun,xmin,xmax)
- 二元 integral2(fun,xmin,xmax,ymin,ymax)
- 三元 integral3(fun,xmin,xmax,ymin,ymax,zmin,zmax)

![image-20210730144946185](C:\Users\nishiyu\AppData\Roaming\Typora\typora-user-images\image-20210730144946185.png)

==被积函数是常数时无法正常运行==

### 线性方程组的解

![image-20210730145906943](C:\Users\nishiyu\AppData\Roaming\Typora\typora-user-images\image-20210730145906943.png)

- 求解命令 x = pinv(A) * b
  - 总是给出唯一解
  - 当方程组有无穷多解时，给出的是最小范数解
  - 当方程组无解时，给的是最小二乘解
- A列满秩时，A\b = pinv(A)*b

### 枚举法

- rem(a , b)取余函数 ，结果是 a % b

#### 退火算法遇到的函数

- randperm()
  - randperm(n) : 返回行向量，包含从1 到 n 没有重复元素的整数随机排列
  - randperm(n , k) : 返回行向量，包含从1 到 n 间随机选择 k 个 唯一整数
- floor()：朝负无穷大四舍五入
  - floor(X)：将X中的每个元素四舍五入到小于或等于该元素的最接近整数
  - 关于秒的用法 (没有重点关注)

- sort：升序排列矩阵，也可以同时返回索引
- find()：
  - find(X)：返回一个包含数组X中每个非0元素元素的线性索引向量
  - find(X , n)：返回前 n 个非 0 元素的索引

#### SVM遇到的函数

- mapstd()：将数据标准化
  - [b,ps] = mapstd(A)  b是按==行==标准化 (均值为0，方差为1) 后的数据 ， ps是各种平均值和方差
  - mapstd('apply' , x , ps)： 利用ps对x进行标准化处理
  - mapstd('reverse' , y , ps): 利用ps对y进行还原

**函数调用**

![image-20210901001320801](C:\Users\nishiyu\AppData\Roaming\Typora\typora-user-images\image-20210901001320801.png)
