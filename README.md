# 小军

TypeScript 小库，零运行时依赖。每份都能在 Node 22 里直接跑测试，不需要安装包。

## 仓库

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

运动、diff、运行时限流。不堆徽章，不写没跑过的数字。
