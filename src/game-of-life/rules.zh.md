# 康威生命游戏规则

_注意: 如果您已熟悉康威的生命游戏及其规则,请跳到下一部分!_

[维基百科对 康威的生命游戏规则 进行了很好的描述: ][wikipedia]

> 生命游戏的宇宙是方形单元的无限二维正交网格,每个方格单元处于两种可能状态之一,活着或死亡,或"填充"或"未填充". 每个细胞与其八个邻居相互作用 - 这八个邻居是水平,垂直或对角相邻的细胞. 在每个步骤中,发生以下转换:
>
> 1. 当前细胞为存活状态时，当周围低于 2 个（不包含 2 个）存活细胞时， 该细胞变成死亡状态。（模拟生命数量稀少）
> 2. 当前细胞为存活状态时，当周围有 2 个或 3 个存活细胞时， 该细胞保持原样。
> 3. 当前细胞为存活状态时，当周围有 3 个以上的存活细胞时，该细胞变成死亡状态。（模拟生命数量过多）
> 4. 当前细胞为死亡状态时，当周围有 3 个存活细胞时，该细胞变成存活状态。 （模拟繁殖）

> 可以把最初的细胞结构定义为种子，当所有在种子中的细胞同时被以上规则处理后, 可以得到第一代细胞图。按规则继续处理当前的细胞图，可以得到下一代的细胞图，周而复始。

[wikipedia]: https://zh.wikipedia.org/wiki/%E5%BA%B7%E5%A8%81%E7%94%9F%E5%91%BD%E6%B8%B8%E6%88%8F

考虑以下初始 Universe:

<img src='../images/game-of-life/initial-universe.png' alt='Initial Universe' width="80" />

我们可以通过考虑每个单元来计算下一代. 左上角的单元格已经死了. 规则 (4) 是适用于死细胞的唯一转换规则. 但是,因为左上角的单元格没有正好三个活动邻居,所以转换规则不适用,并且它在下一代中仍然不存在. 对于 第一行 中的每个其他单元也是如此.

当我们考虑第二列,第三列中的活细胞时,事情变得有趣. 对于活细胞,前三个规则中的任何一个都可能适用. 在这个黑单元的情况下,它只有下面一个活的邻居,因此规则 (1) 适用: 这个单元将在下一代中死亡. 同样的命运也对应着最下面的活黑细胞.

中间活细胞有两个活的邻居: 顶部和底部活细胞. 这意味着规则 (2) 适用,并且它仍然存在于下一代.

最后有趣的案例是中间活细胞左侧和右侧的死细胞. 这三个活细胞都是这些细胞的邻居,这意味着规则 (4) 适用,并且这些细胞将在下一代中存活.

把它们放在一起,我们在下一个滴答之后得到这个宇宙:

<img src='../images/game-of-life/next-universe.png' alt='Next Universe' width=80 />

从这些简单的,确定性的规则出现,奇怪和令人兴奋的行为出现了:

| Gosper 的滑翔机枪                                                                                  | 脉冲星                                                                                 | 太空飞船                                                                                                     |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| ![Gosper's glider gun](https://upload.wikimedia.org/wikipedia/commons/e/e5/Gospers_glider_gun.gif) | ![Pulsar](https://upload.wikimedia.org/wikipedia/commons/0/07/Game_of_life_pulsar.gif) | ![Lighweight space ship](https://upload.wikimedia.org/wikipedia/commons/3/37/Game_of_life_animated_LWSS.gif) |

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/C2vgICfQawE?rel=0&amp;start=65" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>

## 练习

- 手动计算我们的示例 Universe 的下一个滴答. 注意像什么?

<details>
<summary>答案</summary>

它应该是示例宇宙的初始状态:

<img src='../images/game-of-life/initial-universe.png' alt='Initial Universe' width=80 />

这个模式是 _周期性的_：每两个滴答，它就返回到初始状态。

</details>

<br >

- 你能找到一个稳定的初始宇宙吗? 也就是说,每一代人都是一样的宇宙.

<details>

<summary>答案</summary>

有无数稳定的宇宙！平凡稳定的宇宙是空的宇宙。一个二乘二平方的活细胞也是一个稳定的宇宙。

There are an infinite number of stable universes! The trivially stable
universe is the empty universe. A two-by-two square of live cells is also a
stable universe.

</details>
