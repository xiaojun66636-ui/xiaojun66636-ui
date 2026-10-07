# 小军

TypeScript 小库，零运行时依赖。每份都能在 Node 22 里直接跑测试，不需要安装包。

## 仓库

### [breaker](https://github.com/xiaojun66636-ui/breaker)

熔断器。连续失败到阈值就打开，冷却后半开，只放一个试探请求。时钟从外面注入。

### [bloomset](https://github.com/xiaojun66636-ui/bloomset)

布隆过滤器。说「没有」就一定没有，说「有」可能误判。附误判率公式。

### [heapq](https://github.com/xiaojun66636-ui/heapq)

二叉堆。`push` 和 `pop` 都是 O(log n)。默认最小堆，比较函数可以改成最大堆。

### [prefixtrie](https://github.com/xiaojun66636-ui/prefixtrie)

前缀树。按前缀列出 key。删叶子会剪枝，删中间节点只去掉它自己的值。

### [lrushelf](https://github.com/xiaojun66636-ui/lrushelf)

O(1) LRU。哈希表定位，双向链表排新旧，头尾是哨兵节点。`get` 会刷新热度，`has` 不会。

### [hashring](https://github.com/xiaojun66636-ui/hashring)

一致性哈希。虚拟节点，查找是二分。删掉一个节点，只搬走原来落在它弧上的 key。

### [pathroute](https://github.com/xiaojun66636-ui/pathroute)

路径路由。静态段优先于 `:param`，`:param` 优先于末尾 `*wildcard`。同分先注册的赢。

### [backoff](https://github.com/xiaojun66636-ui/backoff)

指数退避加 full jitter，再加一个可注入 sleep 的 retry。不该重试的错误用 `shouldRetry` 挡掉。

### [springstep](https://github.com/xiaojun66636-ui/springstep)

界面运动用的弹簧积分器。走 `m x'' + c x' + k x = 0` 的解析解，掉帧不会像前向欧拉那样炸掉。欠阻尼、临界阻尼、过阻尼三条分支都有测试。

### [linediff](https://github.com/xiaojun66636-ui/linediff)

Myers O(ND) 最短编辑脚本。数组和按行 diff 都能用，附一个 unified diff。正确性对着动态规划的最短距离做了对照，另有一组固定种子的随机用例。

### [gatekeep](https://github.com/xiaojun66636-ui/gatekeep)

令牌桶和滑动窗口限流。时钟从外面注入，测试不用 `sleep`。时钟回拨不会凭空造出令牌。

## 本地验证

```bash
node --experimental-strip-types --test test/*.test.ts
```

## 范围

熔断、布隆过滤器、堆、前缀树、缓存、一致性哈希、路由、重试、限流、diff。不堆徽章，不写没跑过的数字。
