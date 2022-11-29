

# 开关电源设计之：AP法的公式推导

## 1 前提条件

由变压器基本公式可得下列表

| 序号 | 说明                                                |
| :--- | :-------------------------------------------------- |
| 1    | 忽略磁芯的磁阻，全部能量在气隙中                    |
| 2    | 气隙量较大，磁导率 $u_{r} $接近常数，且不触发磁饱和 |
| 3    | 气隙中磁通密度为均匀分布                            |
| 4    | 气隙中磁场强度$H$                                   |

## 2 基本磁心公式

根据法拉第电磁感应定律，绕组中感生的磁动势为
$$
e=N\frac{dΦ}{dt}=\frac{LdI}{dt}  \tag{1.1}
$$


而
$$
Φ=A_{g}B   \\Φ:总磁通
$$
可得
$$
e=NA_{g}\frac{dB}{dt}
$$
设$A_{g}=A_{p}$，其中$A_{p}$为磁心柱面积（忽略边缘效应）



根据安培定律有
$$
mmf=\int Hdl_{g}=H_{lg}=NI \tag{1.2}
$$
磁场的关系式为：
$$
B=u_{r}u_{0}H
$$
而空气的磁导率$u_{r}=1$,因此有
$$
H=\frac{B}{u_{0}} \tag{1.3}
$$
联立式$1.1$，得
$$
e=L\frac{di}{dt}\\edt=Ldi
$$
公式两边同时乘以$I$并积分有
$$
J=\int eIdt=\int LIdi=\frac{1}{2}LI^{2}\tag{1.4}
$$
由式1.2可得
$$
I=\frac{Hl_{g}}{N}\tag{1.5}
$$
式1.5与1.1相乘可得
$$
EI=NA_{g}\frac{dB}{dt}H\frac{l_{g}}{N} \longrightarrow EIdt=A_{g}L_{g}HdB
$$
两边积分可得
$$
\int EIdt =J = A_{g}L_{g}\int HdB \tag{1.6}
$$
又因为$H=\frac{B}{u_{0}}$，即磁通等于场强乘磁阻有：
$$
J = A_{g}L_{g}\int \frac{B}{u_{0}}dB =\frac{A_{g}L_{g}}{u_{0}} \int {B}dB=\frac{1}{2}\frac{A_{g}L_{g}}{u_{0}} B^{2}
$$
再次因为$H=\frac{B}{u_{0}}$，可得
$$
J =\frac{1}{2}A_{g}L_{g}BH \tag{1.7}
$$
联立式子1.4与式1.7可得
$$
\frac{1}{2}LI^{2} =\frac{1}{2}A_{g}L_{g}BH \tag{1.8}
$$
又因为式1.2有$NI=HI_{g}$带入式1.8中可得：
$$
\frac{1}{2}LI^{2} =\frac{1}{2}BA_{g}NI \longrightarrow LI=BA_{g}N\longrightarrow N=\frac{LI}{BA_{g}}\tag{1.9}
$$
其中$I$是峰值电流

现在考虑到绕组：安匝数等于导线中的电流密度$I_{a}$乘以填充系数$K_{u}$修改的有效窗口面积$A_{w}$
$$
NI_{rms}=I_{a}A_{w}K_{u}\longrightarrow N=\frac{I_{a}A_{w}K_{u}}{I_{rms}} \tag{1.10}
$$

## 3 结论推导(公式部分)

联立式1.9和1.10得：
$$
\frac{LI}{BA_{g}}=\frac{I_{a}A_{w}K_{u}}{I_{rms}}
$$
AP法中$AP=A_{w}A_{g}$为：
$$
AP=A_{w}A_{g}=\frac{LII_{rms}10^4}{I_{a}K{u}B} \tag{1.11}
$$

## 4 结论推导（文字部分）

在连续电流的变压器中，峰值电流幅值$I$非常接近于有效电流值$I_{rms}$，因此有$I\times I_{rms} \approx I^2$.此外，在大多数应用中，电流密度$I_{a}$、填充系数$K_{u}$和峰值磁通密度$B$被当做常数处理，因此式子$(1.11)$可以将AP值与储存的能量联系起来（功率处理能力）。从而将AP值应用到磁芯的选择中。





### 日常美图收藏

![lofter_1638801868051.jpg](http://tva1.sinaimg.cn/large/005Q1GhGly1h5npgkirl7j310r1k4k5k.jpg)