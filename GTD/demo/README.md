## 数据预处理

具体见 [数据预处理](../01-数据预处理.ipynb).

### 特征列的选择

首先, 本文舍弃缺失值超过 $90\%$ 的特征列, 通过计算得到剩下的特征列占总特征的比例为 $53\%$, 然而剩下的特征中缺失值比例在 $50\% \sim 90\%$ 仅仅占其 $19\%$, 因而, $0.19 \times 0.53 \approx 10\%$, 故而, 本文仅仅选择缺失值比例小于 $50\%$ 的特征对于研究任务的影响不大. 记缺失值比例小于 $50\%$ 的特征组成的数据矩阵为 $features$.

### 任务 1 依据危害性对恐怖袭击事件分级

记

```py
num_feature_names = {
    'nperps', 'nperpcap', 'nkill', 'nkillus', 'nkillter', 'nwound',
    'nwoundus', 'nwoundte', 'propvalue', 'nhostkid', 'nhostkidus',
    'nhours', 'ndays', 'ransomamt', 
    'ransomamtus', 'ransompaid','ransompaidus', 'nreleased'
}
```

为数值变量集合. 本文取数值变量集合与 $features$ 的特征列集合的交集作为可计算的数值变量 $\text{cal_df}$, 具体见下表:

变量|说明
:-:|:-:
`nkillus`|美国死亡人数
`nkillter`|凶手死亡人数
`nperpcap`|抓获的凶手数量
`nwoundus`|美国受伤人数
`nperps`|凶手数量
`nwoundte`|凶手受伤人数
`nkill`|死亡总数
`nwound`|受伤总数

查看其具体信息:

```json
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 114183 entries, 0 to 114182
Data columns (total 8 columns):
nperps      101017 non-null float64
nkillus     113815 non-null float64
nkill       109903 non-null float64
nperpcap    110815 non-null float64
nwound      105951 non-null float64
nkillter    111507 non-null float64
nwoundte    109678 non-null float64
nwoundus    113606 non-null float64
dtypes: float64(8)
```

即此时可以用来做计算的特征总共有 $8$ 个, 并且该数据集的样本数为 $114183$. 其缺失值的分布如下:

```json
nperps      13166
nkillus       368
nkill        4280
nperpcap     3368
nwound       8232
nkillter     2676
nwoundte     4505
nwoundus      577
```

