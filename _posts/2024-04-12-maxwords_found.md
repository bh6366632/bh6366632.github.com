---
layout: post
title:  "maxwords_found"
date:   2024-04-08 11:36
categories: PYTHON
permalink: /archivers/maxwords_found
---

[문제]:https://leetcode.com/problems/maximum-number-of-words-found-in-sentences/

# 문제
A sentence is a list of words that are separated by a single space with no leading or trailing spaces.

You are given an array of strings sentences, where each sentences[i] represents a single sentence.

Return the maximum number of words that appear in a single sentence.

> Input: sentences = ["alice and bob love leetcode", "i think so too", "this is great thanks very much"]
> 
> Output: 6

# 코드
```
class Solution(object):
    def mostWordsFound(self, sentences):
        s=0
        for i in sentences:
            S=i.split()
            if len(S)>s:
                s=len(S)
        return s
```
이 문제에서는 리스트에 입력된 문장들중 단어가 최대 몇번이나 들어갔는지 구하는 문제이다
- 횟수를 저장할 `s` 함수 선언
- `for`문에 `sentences` 대입
- `S`에 `i`값을 `split()`을 사용해서 문장에 단어들을 나눠준다.
- `if`문으로 현제 최대값 `s` 보다 나눠진 단어 길이가 길면 `s`에 저장해준다
