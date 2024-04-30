---
layout: post
title:  "manybumbers"
date:   2024-04-29  12:23
categories: PYTHON
permalink: /archivers/manybumbers
---

[문제]:https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/description/
# [문제]

1365. How Many Numbers Are Smaller Than the Current Number

Given the array nums, for each nums[i] find out how many numbers in the array are smaller than it. That is, for each nums[i] you have to count the number of valid j's such that j != i and nums[j] < nums[i].

Return the answer in an array.

>input  : `nums = [6,5,4,8]`  
>output  : `[2,1,0,3]`   
>`6`보다 작은 값 2개 `[5,4]`   
>`5`보다 작은 값 1개 `[4]`   
>`4`보다 작은 값 0개   
>`8`보다 작은 값 3개 `[6,5,4]`   

# 풀이

이 문제는 `nums`리스트를 입력받는다. 그리고 입력받은 `nums` 에서 `nums[i]`값 보다 작은 값이 있는지확인하고 그 갯수를 리스트형태로 `return` 해주는 문제이다.

```
class Solution(object):
    def smallerNumbersThanCurrent(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        output=[]
        i=0
        while i< len(nums):
            count=0
            j=0
            while j<len(nums):
                if nums[i] >nums[j] and not i == j:
                    count+=1
                j+=1
            output.append(count)
            i+=1
        return output
n=Solution()
n.smallerNumbersThanCurrent([8,1,2,2,3])
```

코드를 보면 중첩 `while` 문을 사용하여 조건문 `if`를 사용해서 `nums[i]` 값보다 다른인덱스 `nums[j]`에있는값이 작고 `not i == j`를 사용해서 같은 인덱싱값을 
비교하지않게하고 모든 조건이 참일경우에 `count`값에 1을 더하면서 `nums[i]` 보다 작은값이면 카운트해준다. 그다음에 j에1을 더하며 비교하는 값을 바꿔주고
반복문이 다돌아서 `num[i]`값과 다 비교했으면 i값의 1을 증가시켜 다음값도 비교해주고 `i`가 `nums`에 길이까지 다 돌았을때 `output` 값을 리턴해준다.
