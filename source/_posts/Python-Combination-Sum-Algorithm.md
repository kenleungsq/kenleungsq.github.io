---
title: Python Combination Sum Algorithm
date: 2024-01-27 17:32:00
tags:
categories:
  - [Python, Algorithm]
---

***

# 一组数字中和为target的所有组合

```Python
def combinationSum2(candidates, target):
    def dfs(pos: int, rest: int):
        nonlocal sequence
        if rest == 0: #rest为target
            ans.append(sequence[:])
            return
        if pos == len(freq) or rest < freq[pos][0]: #freq为已排升序的tuple list，如果要找的和比list中最少的数还少，则找不到任何组合
            return
        dfs(pos + 1, rest)
        most = min(rest // freq[pos][0], freq[pos][1])
        most = int(most)
        for i in range(1, most + 1):
            sequence.append(freq[pos][0])
            dfs(pos + 1, rest - i * freq[pos][0])
        sequence = sequence[:-most]
    freq = sorted(collections.Counter(candidates).items())
    ans = list()
    sequence = list()
    dfs(0, target)
    return ans```
