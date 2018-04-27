<!-- TOC -->
* [��һ��](#��һ��)
* [�ڶ���](#�ڶ���)
* [������](#������)
* [������](#������)
* [������](#������)
* [������](#������)
* [������](#������)
* [�ڰ���](#�ڰ���)
<!-- TOC -->

## ��һ��

### ��Ŀ����
>ƽ������n�����Σ����½�����(x1[i],y1[i])�����Ͻ�����(x2[i],y2[i])���ж��ص����������Ŀ�Ƕ��١�������������������й�����������Ϊ�������ص��ģ������Ǳ߽�ͽ��䡣������ƽ�����ص��������ĵط��ľ�����Ŀ��

**��������:**
>����������У���һ�б�ʾ������Ŀn���ڶ���x1-->���½Ǻ����꣬������y1-->���½������꣬������x2-->���ϽǺ����꣬������y2-->���Ͻ������ꡣ

**�������:**
>�������ص��ľ�����Ŀ����������ص����1.

### ����˼·
- �������һ�����������ķ�ʽ�������Ե�һ��Ϊ��׼���Ժ���ľ��ν����������жϣ�������룬���֦��������������ص�������Ҫ�������Ƿ�������ص������ڵģ������ߵݹ��������ֵ���ɡ�ͬʱ����Ҫ��ÿ����Ϊ��׼����������һ�Σ�����̰��˼�뱣�����ֵ��



## �ڶ���

### ��Ŀ����
>ţţ��ǰ����ʦ����õ���һ�����������ԣ�x,y����ţţ�������Ǿ����Ƕ����ˡ�����ţţ�ǵ���ʦ������x��y��������n,����x����y���������ڵ���k��ţţϣ�����ܰ�������һ���ж��ٸ����ܵ����ԡ�

**��������:**
>�����������������n,k(1<=n<=10^5,0<=k<=n-1)

**���������**
>����ÿ���������������һ����������ʾ���ܵ�����������

**���ӣ�**

���룺
```
5 2
```
���
```
7
```
˵��
```
���������������У���2,3����2,4����2,5����3,4����3,5����4,5����5,3��
```

### ����˼·

- ����ѭ������
- ����ÿ��ѭ����������������k��Ԫ�صĸ���,�Լ�ʣ�µ�һ��ѭ����������������������ڵ���k��Ԫ�صĸ���
- ����
```
n=10 k=2
i= 1  %  3 =  1
i= 2  %  3 =  2
i= 3  %  3 =  0
i= 4  %  3 =  1
i= 5  %  3 =  2
i= 6  %  3 =  0
i= 7  %  3 =  1
i= 8  %  3 =  2
i= 9  %  3 =  0
i=10  %  3 =  1
```

## ������

### ��Ŀ����
>Ϊ���ҵ��Լ�����Ĺ�����ţţ�ռ���ÿ�ֹ������ѶȺͱ��ꡣţţѡ�����ı�׼�����ѶȲ�������������ֵ������£�ţţѡ�񱨳���ߵĹ�������ţţѡ�����Լ��Ĺ�����ţţ��С���������ţţ��æѡ������ţţ��Ȼʹ���Լ��ı�׼������С����ǡ�ţţ��С���̫���ˣ�������ֻ�ð�������񽻸����㡣

**��������:**
>ÿ���������һ������������
ÿ�����������ĵ�һ�а����������������ֱ��ʾ����������N(N<=100000)��С��������M(M<=100000)��
��������N��ÿ�а����������������ֱ��ʾ��������Ѷ�Di(Di<=1000000000)�ͱ���Pi(Pi<=1000000000)��
��������һ�а���M�����������ֱ��ʾM��С��������ֵAi(Ai<=1000000000)��
��֤������������ı�����ͬ��

**�������:**
>����ÿ��С��飬�ڵ�����һ�����һ����������ʾ���ܵõ�����߱��ꡣһ���������Ա������ѡ��

**��������1:**
```
3 3
1 100
10 1000
1000000000 1001
9 10 1000000000
```

**�������1:**
```
100
1000
1001
```

### ����˼·
- ά��һ����N+M����dp[N+M]�����飬��¼��ͬ�����Ͳ�ͬ�Ѷ��µ����н��
- ���Ӷ� MAX��O(NlogN),O(MlogM),O(N+M))

![](https://github.com/LyricYang/Internet-Recruiting-Algorithm-Problems/blob/master/2018/NETEASE/pic/Q3.png)



## ������

### ��Ŀ����
>СQ�õ�һ�����������: 1, 12, 123,...12345678910,1234567891011...��
����СQ�����ܷ�3����������ʺܸ���Ȥ��
СQ����ϣ�����ܰ�������һ�´����еĵ�l������r��(�����˵�)�ж��ٸ������Ա�3������

**��������:**
>���������������l��r(1 <= l <= r <= 1e9), ��ʾҪ�����������ˡ�

**�������:**
>���һ������, ��ʾ�������ܱ�3���������ָ�����

**��������1:**
```
2 5
```

**�������1:**
```
3
```

**����˵��1:**
```
12, 123, 1234, 12345...
����12, 123, 12345�ܱ�3����
```

### ����˼·
- ÿ�����ּ������ܱ�3����
- ����ѭ��������Ϊ2��0��������


## ������

### ��Ŀ����
>СQ���ڸ�һ������Ϊn�ĵ�·���·�ư��÷�����
Ϊ�����������,СQ�ѵ�·��Ϊn������,��Ҫ�����ĵط���'.'��ʾ, ����Ҫ�������ϰ��������'X'��ʾ��
СQ����Ҫ�ڵ�·������һЩ·��, ���ڰ�����posλ�õ�·��, ��յ·�ƿ�������pos - 1, pos, pos + 1������λ�á�
СQϣ���ܰ��þ����ٵ�·����������'.'����, ϣ�����ܰ�������һ��������Ҫ����յ·�ơ�

**��������:**
>����ĵ�һ�а���һ��������t(1 <= t <= 1000), ��ʾ����������
������ÿ����һ����������, ��һ��һ��������n(1 <= n <= 1000),��ʾ��·�ĳ��ȡ�
�ڶ���һ���ַ���s��ʾ��·�Ĺ���,ֻ����'.'��'X'��

**�������:**
>����ÿ����������, ���һ����������ʾ������Ҫ����յ·�ơ�

**��������1:**
```
2
3
.X.
11
...XX....XX
```

**�������1:**
```
1
3
```

### ����˼·
- ��Ϊ·��ֻ����������λ�ã����Խ���·����ֳ�����һ��������ۣ�����8�����
- ��������������������һ��λ����'.'����·������1���������������һ��λ����'X'�����±�������һλ���½��з��鿼��

```
...  ..X  .X.  .XX
XXX  XX.  X.X  X..
```


## ������

### ��Ŀ����
>ţţȥ�Ġ���ʦ�Ҳ��Σ����ŵ�ʱ�����򱱷���������������·�ˡ���Ȼ��������һ�ŵ�ͼ����������Ҫ֪���Լ������ĸ���������������

**��������:**
>ÿ���������һ������������
ÿ�����������ĵ�һ�а���һ������������ʾת����Ĵ���N(N<=1000)��
��������һ�а���һ������ΪN���ַ�������L��R��ɣ�L��ʾ����ת��R��ʾ����ת��

**�������:**
>���ţţ�������ķ���N��ʾ����S��ʾ�ϣ�E��ʾ����W��ʾ����

**��������1:**
```
3
LRR
```

**�������1:**
```
E
```

### ����˼·

- ��������ͬ��������ת��ת������Ĳ�ͬ���򣬼�ģ�����߹��̡�


## ������

### ��Ŀ����
>ţţ����˯��ͷ�����������˺ܶ����ӣ�ֻ�����������ʱ�����Ż��ѹ������Ҿ������𴲡���������������ҪX���ӵ�����ң��Ͽ�ʱ��Ϊ�����AʱB�֣���������������ʲôʱ���𴲡�

**��������:**
>ÿ���������һ������������
ÿ�����������ĵ�һ�а���һ������������ʾ���ӵ�����N(N<=100)��
��������N��ÿ�а���������������ʾ������������ʱ��ΪHi(0<=Hi<24)ʱMi(0<=Mi<60)�֡�
��������һ�а���һ����������ʾ������������ҪX(0<=X<=100)���ӵ�����ҡ�
��������һ�а���������������ʾ�Ͽ�ʱ��ΪA(0<=A<24)ʱB(0<=B<60)�֡�
���ݱ�֤������һ�����ӿ�����ţţ��ʱ������ҡ�

**�������:**
>�������������ʾţţ������ʱ�䡣

**��������1:**
```
3 
5 0 
6 0 
7 0 
59 
6 59
```

**�������1:**
```
6 0
```

### ����˼·

- ��ʱ�ָ�ʽ��ʱ��ת��Ϊ���ӱ�ʾ��ʱ�䣬�ҵ�����С����ʱ�䣨�Ͽ�ʱ��-·��ʱ�䣩������ʱ��



## �ڰ���

### ��Ŀ����
>ţţ׼���μ�ѧУ��֯�Ĵ���, ����ǰţţ׼����������װ��һЩ��ʳ, ţţ�ı�������Ϊw��
ţţ����һ����n����ʳ, ��i����ʳ���Ϊv[i]��
ţţ��֪������������������������������,��һ���ж�������ʳ�ŷ�(�����Ϊ0Ҳ��һ�ַŷ�)��


**��������:**
>�����������
��һ��Ϊ����������n��w(1 <= n <= 30, 1 <= w <= 2 * 10^9),��ʾ��ʳ�������ͱ�����������
�ڶ���n��������v[i](0 <= v[i] <= 10^9),��ʾÿ����ʳ�������

**�������:**
>���һ��������, ��ʾţţһ���ж�������ʳ�ŷ���

**��������1:**
```
3 10
1 2 4
```

**�������1:**
```
8
```

**����˵��1:**
>������ʳ�����С��10,����ÿ����ʳ�з���Ͳ��������������һ����2*2*2 = 8�������