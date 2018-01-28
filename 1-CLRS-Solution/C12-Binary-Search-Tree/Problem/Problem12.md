## 12-1
* （1）小于才向左走，所以一直向右，最后复杂度为$O(n)$
* （2）每次改变向左还是向右走
```cpp
    Insert(x)
        p = root
        while(p)
            y = p
            if(p < x)
                p = p.left
            else if(p == x)
                if(p.flag == 1)
                    p.flag = 0
                    p = p.left
                else
                    p.flag = 1
                    p = p.right
            else
                p = p.right
        p = x
        if(y > p)
            y.left = p
        else if(y == p)
            if(y == 1)
                y.right = p
            else
                y.left = p
        else
            y.right = p
 ```
* （3）相当于增加一个链表进去（类比hash），相同的值放入同一个链表，可以采用后来的值插入链表开头，$O(nlgn)$
和插不相同的值没什么区别，很好实现
* （4）可以以等概率选择左子树或者右子树，很好实现

## 12-2
前序遍历即可，详细内容见code

## 12-3

* （1）这就是$P(T)$的定义。所有的深度求和
* （2）增加根节点进去，将使除了根节点以外的节点深度全部加一，共$n-1$个节点，也就是这个结果。
* （3）很简单，平均的定义，每个大小的左子树和右子树都平均得取到了。
* （4）进行变形
* （5）使用代入法，参考快速排序一节的证明方法。
* （6）快速排序第一次的分界点便是二叉树的根节点，然后每一个子树的根节点就是递归快排取的那些点。

## 12-4
这是一个我很久就想知道的问题......
* （1）左子树有$b_k$种，右子树有$b_{n-1-k}$种，所以这种划分条件就是两者乘起来
* （2）使用生成函数求这个结果的通项公式，，
* 决定重学微积分，，，shit