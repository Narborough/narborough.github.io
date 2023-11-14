---
layout: post
title: LeetCode Day1
date: 2023-11-14 23:16:00 +0900
categories: algo
tags: LeetCode
---

Day1 at leetcode.  
e-mail confirmation completed.  
Starting with easy problems to be acquainted with the platform.  
Going to use Python3. Maybe more languages for later.  

problem: https://leetcode.com/problems/running-sum-of-1d-array  
```
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        r = [0]
        for n in nums:
            r.append(r[-1] + n)
        return r[1:]
```

problem: https://leetcode.com/problems/richest-customer-wealth  
```
class Solution:
    def maximumWealth(self, accounts: List[List[int]]) -> int:
        max = 0
        for customer in range(0, len(accounts)):
            sum = 0
            for account in accounts[customer]:
                sum += account
            if max <  sum:
                max = sum
        return max
```

problem: https://leetcode.com/problems/fizz-buzz  
```
class Solution:
    def fizzBuzz(self, n: int) -> List[str]:
        r = []
        for i in range(1, n+1):
            t = i % 3
            f = i % 5
            if t == 0:
                if f == 0:
                    r.append("FizzBuzz")
                else:
                    r.append("Fizz")
            elif f == 0:
                r.append("Buzz")
            else:
                r.append(f"{i}")
        return r
```

problem: https://leetcode.com/problems/number-of-steps-to-reduce-a-number-to-zero  
```
class Solution:
    def numberOfSteps(self, num: int) -> int:
        cnt = 0; s = num
        while(s != 0):
            if s % 2 == 0:
                s = s / 2
            else:
                s += -1
            cnt += 1
        return cnt
```

problem: https://leetcode.com/problems/middle-of-the-linked-list  
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        cur = head; nodes = []
        while(cur != None):
            nodes.append(cur)
            cur = cur.next
        m = len(nodes) / 2
        return nodes[int(m)]
```

problem: https://leetcode.com/problems/ransom-note  
```
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        s = ransomNote
        for c in magazine:
            s = s.replace(c, "", 1)
        return s == ""
```
