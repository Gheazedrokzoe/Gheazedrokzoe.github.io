---
title: solution-at-agc044-c
date: 2024-01-25 23:20:22
tags:
  - 题解
  - atcoder
  - agc
published: true
hideInList: false
feature: 
isTop: false
---
sto nantf orz

## 正文

算得上相当有意思以及启发性的数据结构题了。

三进制表示联想到我们可以建立一个三叉树。类似于 Trie 一样的，按三进制从低位到高位建立一个 Trie 树。一个非常好的性质这是一个完美三叉树。

接下来我们可以考虑怎么维护每一种操作。

#### Salasa 舞
对于这种操作，相当于对于树上每一个点都交换他们的 1,2 两个儿子。打个标记即可支持。

#### Rumba 舞
这相当于什么呢？我们发现，相当于把原来的 0 号儿子给到 1 号儿子，把原来的 1 号儿子给到 2 号儿子，把原来的 2 号儿子给到 0 号儿子。前两者没有进位，所以不用管，发现原来 2 号儿子会产生一个进位操作。这相当于什么呢？这相当于在这个儿子子树内再进行一次 Rumba 舞操作。递归求解即可。

总复杂度 $O(3^n+Tn)$

[code](https://atcoder.jp/contests/agc044/submissions/49335959)