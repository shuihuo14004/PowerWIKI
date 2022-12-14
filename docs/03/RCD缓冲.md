# DRC缓冲电路

开门见山的二三话，本笔记内容来自[精通开关电源 第三版](http://book.ucdrs.superlib.net/views/specific/2929/bookDetail.jsp?dxNumber=000016699901&d=6225A464664218147A690588A6CF6297&fenlei=18160906)



<center><img src=" https://tva1.sinaimg.cn/large/005Q1GhGly1h8sp20ewdbj30l10b179a.jpg " width="70%"></center>

$$
图1
$$



# 1 理论基础部分

## 1.1  导论

缓冲网络（经常是由损耗型的电阻、电容和二极管网络组成的网络）是并联在高压开关器件和整流二极管两端的，用来减少由开关器件导通或关断而产生的开关应力与电磁干扰问题。

当用到双极型晶体管时，缓冲网络就用来提供一个“负载线整形”功能，确保副边击穿反向偏压以及安全工作区的限定值不被超越。在离线式反激变换器中，存在很大的反激电源 , 所以缓冲网络的用途特别重要。



## 1.2 具有负载线整形的缓冲电路

在图2(a)中显示了传统单端输出反激变换器的基本电路， 它包括由$Q_{1}$驱动的变压器原边$P_{1}$ 、带有漏感能量恢复绕组的$P_{2}$以及二极管 $D_{2}$。 缓冲网络由元件 $D_{1}$、 $C_{1}$ 和$R_{1}$组成，它并联在$Q_{1}$的集电极与发射极之间。

图2(b)中显示的是在这个电路中所期望的电压和电流波形。如果要求有“负载线整形” 功能， 那么缓冲网络元器件的主要功能是在$Q_{1}$关断期间为维持变压器原边感应电流$I_{P}$提供一个高频交流信号通路。由于该缓冲网络的存在，在关断$Q_{1}$时就不会在集电极形成一个大电 压，$Q_{1}$集电极的实际电压值主要与分流电流$I_{s}$的幅值、缓冲电容$C_{1}$的值以及$Q_{1}$的关断时间$t_{1}-t_{2}$有关。如果没有这个缓冲网络，$Q_{1}$上的电压降将非常大。改电源降由初极漏感以及关断电流的变化率$\frac{di}{dt}$来决定。

在关断沿缓冲网络降低集电极电压的变化率 ， 因此也就减少了射频干扰问题。



<center><img src=" https://tva1.sinaimg.cn/large/005Q1GhGly1h8sqd3d9tcj307f071dg9.jpg " width="40%"></center>

$$
图 （a）反激变换器中的RC缓冲电路
$$

<center><img src=" https://tva1.sinaimg.cn/large/005Q1GhGly1h8squ3smx0j307y0cudgt.jpg " width="40%"></center>

$$
图(b) RC缓冲网络的电压电流波形
\\图 2
$$

## 1.3 工作过程

稳定状态下， $Q_{1}$关断期间的工作过程见图2。
见图2(b)在$t_{1}$时刻$Q_{1}$开始关断时$T_{1}$的原边电感与漏感，将使变压器原边绕组中的原边电流$I_{p}$保持不变。这将导致$Q_{1}$的集电极电压从$t_{1}$到$t_{2}$会上升，原边电流分出一部分电流$I_{s}$到$D_{1}$和$C_{1}$,  使$C_{1}$在此时充电。

因此， 当流过$Q_{1}$的电流下降 ， 电感强迫分流电流$I_{s}$流过二极管$D_{1}$给$C_{1}$充电。如果$D_{1}$在有利的情况下快速关断， 那么集电极电压的变化率$\frac{dV_{C}}{dt}$将只与原来的集电极电流$I_{P}$以及$C_{1}$的电容值有关。

可得
$$
\frac{dV_{C}}{dt}=\frac{I_{P}}{C_{1}}
$$
当$Q_{1}$关断后，恒定电流充电使集电极电压线性增大， 直到在$t_{3}$时刻达到反向钳位电压$2V_{DC}$,  这时$D_{3}$也导通。在$t_{3}$时刻之后不久（该延时时间与原边－副边漏感的大小有关），副边绕组的输出电压就会增大到与输出电容上的电压值相等。这时反激电流将会从原边变换到副边电路，该电流是以一定的速率（由副边漏感与通过$D_{2}$，$C_{2}$的外部回路电感决定）建立起来（在$t_{3}-t_{4}$ 内）。

实际上，$Q_{1}$不会马上关断， 因此， 要避免发生二次击穿， 应该合理选择缓冲网络， 在集电极电流变为零之前， 使$Q_{1}$集电极电压不会超过$V_{ceo}$。

如果不使用缓冲网络，图3中的$a$和$b$显示相对较高的边沿损耗和二次击穿负载线的应力。

如果使用合适的缓冲网络， 便可获得图3的$c$和$d$所示更好的关断波形。

<center><img src=" https://tva1.sinaimg.cn/large/005Q1GhGly1h8sssx7zf3j309e0dfabf.jpg " width="60%"></center>

$$
图3  \\(a)没有缓冲网络电 路的接通和关断电压、电流以及损耗应力
\\(b)没有负载线修整时影响反向偏置安全工作区 ( RBSOA ) 的动态负载线的限制
（注意二次侧的破坏应力）
\\(c) 有缓冲网 络电路的接通和关断电压、电流以及损耗强度
\\(d) 基千负载线整形的负载线与 RBSOA 限制
$$

# 2  经验值预估缓冲网络元件值

重新参考图1(a),  除非$Q_{1}$的关断时间为已知（在最大集电极电流状况的条件下），否则缓冲网络中最佳的 $C_{1}$值就只能根据经验来选择， 这可依据实测的集电极关断电压、关断电流和关断时间来决定。

$C_{1}$最小值的选择应满足安全电压范围 ， 此电压范围在晶体管$V_{eco}$额定值与在集电极电流到0时$T_{2}$的实际集电极电压之间，这里至少有30%范围的余量，来对应考虑缓冲网络元件参数的变化及温度影响 。

驱动电路的设计、集电极电流的加载以及工作温度都对$Q_{1}$的开关速度有相当大的影响。应避免选用大的$C_{1}$ 值， 因为在反激作用结束后存储在$C_{1}$中的能量会在$Q_{1}$下一个导接通期间消耗在$R_{1}$上。

$R_{1}$值的选择是一个折中的选择。在$Q_{1}$导通边沿，$R_{1}$ 的低阻值将导致$Q_{1}$上形成大电流，这带来过大的导通损耗。另一方面，如果$R_{1}$的阻值非常大，那么在极短的导通期间内将不能使$C_{1}$充分放电。

动态加载情况包括在满载时和最大输入电压情况下的初始导通、宽和窄的脉冲条件以及输出短路。 建议在此情况下，要仔细检查$Q_{1}$的集电极电流和集电极电压波形。对于该类型的缓冲网络来说，必须总是折中考虑$R_{1}$和$C_{1}$的选择。

# 3计算求得缓冲元件参数

在集电极电流变为0的$t_{2}$时刻，$C_{1}$的选择应该满足：使$Q_{1}$的集电极-发射极电压$V_{ce}$是$V_{ceo}$额定值的70%。

假设原边电感在关断沿期间可以保持原边电流不变，$Q_{1}$的集电极电流在$t_{1}-t_{2}$期间是线性减小的，那么在此时间段内流入缓冲网络的电流$I_{s}$会线性增加。

集电极电流的下降时间$t_{1}-t_{2}$可从生产厂商的数据表那里得到，也可通过在集电极的在最大电压与最大电流值条件下 的动态驱动状态下测量得到，双脉冲测试。

假设已知集电极电流的下降时间为$t_{1}-t_{2}$,  在$Q_{1}$集电极电流下降期间$t_{1}-t_{2}$ ,  流过$C_{1}$上的电流$I_{s}$将会从中线性增大到$I_{p}$。因此在这段时间内流过$C_{1}$的平均电流为$\frac{I_{P}}{2}$。若已知最大的原边电流$I_{p}$与关断时间$t_{1}-t_{2}$, 那么最佳的$C_{1}$值为：
$$
\frac{dV_{C}}{dt}=\frac{I_{p}}{ZC_{1}}
$$


假设集电极电流是线性斜坡变化的波形 ，则在关断期间流过$C_{1}$的平均电流就是峰值电流值的$\frac{1}{2}$, 见图1(b)。

如在$t_{2}$的集电极电流变为零时，集电极电压值不超过$V_{ceo}$值的70% , 那么：
$$
C_{1}=\frac{I_{P}t_{t}}{2\times(0.7\times V_{ceo})}
$$


| 符号      | 意义                                                 |
| --------- | ---------------------------------------------------- |
| $I_{P}$   | 最大原边电流                                         |
| $t_{t}$   | $Q_{1}$集电极电流的下降时间$t_{1}-t_{2}$，单位为$us$ |
| $V_{ceo}$ | 额定电压$V$                                          |
| $C_{1}$   | 缓冲网络电容，$uF$                                   |

# 4 开关管$Q_{1}$的关断损耗

按照上面所说的方法， 尽管波形已经反向， 在关断期间，$C_{1}$和晶体管$Q_{1}$上都有类似的平均电流与电压。在关断时间$t_{1}-t_{2}$内，开关管的功耗与在关断结束时刻$t_{2}$存储在$C_{1}$上的能量相等。因此：


$$
P_{Q_{1}(off)}=\frac{1}{2}\times C_{1}(0.7V_{ceo})^{2}f
$$


| 符号             | 意义                                |
| ---------------- | ----------------------------------- |
| $P_{Q_{1}(off)}$ | 关断期间内$Q_{1}$的功耗，单位是$mW$ |
| $C_{1}$          | 缓冲网络电容，单位为$uF$            |
| $V_{ceo}$        | 额定电压$V$                         |
| $f$              | 频率，$kHZ$                         |





# 5 缓冲网络的电阻值

缓冲网络中放电电阻$R_{1}$被用来在已定义的最小导通期间内使缓冲网络电容$C_{1}$放电。

最小的导通时间由在最大输入电压以及最大工作频率条件下所定义的最小负载决定。

$CR$时间常数应该小于最小导通时间的50% ,  保证$C_{1}$能够在下一个关断时间前进行有效的放电。

因此：
$$
R_{1}=\frac{1}{2} \times \frac{t_{on(min)}}{C_{1}}
$$

# 6 缓冲网络中电阻值的能耗

每个周期内，在缓冲网络中的电阻功耗等于关断结束时存储在电容$C_{1}$的能量，而$C_{1}$上的电压与变换器电路的类型有关。

根据能量守恒，$C_{1}$上的电压将等于电源电压$V_{cc}$因此在下个导通期间到来之前，所有的反向电压都会降为零值。对于连续工作方式，$C_{1}$上的电压就等于电源电压与变压器副边反射到原边的电压之和。

在$C_{1}$放电前的电压是$V_{c}$, 则$R_{1}$的功耗用以下公式计算：
$$


P_{R_{1}}=\frac{1}{2} \times C_{1V_{c}}^{2}f
$$
