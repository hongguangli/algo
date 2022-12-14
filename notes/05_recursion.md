# 递归

**递归需要满足的三个条件**

**1. 一个问题的解可以分解为几个子问题的解**

何为子问题？子问题就是数据规模更小的问题。比如，前面讲的电影院的例子，你要知道，“自己在哪一排”的问题，可以分解为“前一排的人在哪一排”这样一个子问题。

**2. 这个问题与分解之后的子问题，除了数据规模不同，求解思路完全一样**
   
比如电影院那个例子，你求解“自己在哪一排”的思路，和前面一排人求解“自己在哪一排”的思路，是一模一样的。

**3. 存在递归终止条件**
   
把问题分解为子问题，把子问题再分解为子子问题，一层一层分解下去，不能存在无限循环，这就需要有终止条件。

## 如何编写递归代码？

写递归代码最关键的是写出**递推公式**，找到**终止条件**。

写递归代码的关键就是找到如何将**大问题分解为小问题**的规律，并且基于此写出递推公式，然后再推敲终止条件，最后将递推公式和终止条件翻译成代码。

当我们看到递归时，我们总想把递归平铺展开，脑子里就会循环，一层一层往下调，然后再一层一层返回，试图想搞清楚计算机每一步都是怎么执行的，这样就很容易被绕进去。

如果一个问题 A 可以分解为若干子问题 B、C、D，你可以假设子问题 B、C、D 已经解决，在此基础上思考如何解决问题 A。而且，你只需要思考问题 A 与子问题 B、C、D 两层之间的关系即可，不需要一层一层往下思考子问题与子子问题，子子问题与子子子问题之间的关系。屏蔽掉递归细节，这样子理解起来就简单多了。

## 递归代码要警惕堆栈溢出

如果递归求解的数据规模很大，调用层次很深，一直压入栈，就会有堆栈溢出的风险。

### 如何避免出现堆栈溢出呢？

可以通过在代码中限制递归调用的最大深度的方式来解决这个问题。递归调用超过一定深度（比如 1000）之后，我们就不继续往下再递归了，直接返回报错。

### 递归代码要警惕重复计算

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    src="https://raw.githubusercontent.com/hongguangli/Figures/main/20221206184745.png" width=500>
</center>

我们可以通过一个数据结构（比如散列表）来保存已经求解过的 f(k)。

**递归代码虽然简洁高效，但是，递归代码也有很多弊端。比如，堆栈溢出、重复计算、函数调用耗时多、空间复杂度高等，所以，在编写递归代码的时候，一定要控制好这些副作用。**