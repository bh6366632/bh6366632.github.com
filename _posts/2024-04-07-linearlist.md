---
layout: post
title:  "linearlist"
date:   2024-04-07 08:57
categories: PYTHON
permalink: /archivers/linearlist
---

<h1> 선형리스트 내용 정리</h1>

- 선형리스트(Linear List)의 정의
- 선형리스트(Linear List)란 **데이터를 일정한순서**로 나열한 자료구조
- 순차 리스트(Ordered List)라고도 한다.

# 전체 코드
```
def add_data(friend) :
    
	katok.append(None)
	kLen = len(katok)
	katok[kLen-1] = friend


def insert_data(position, friend) :    
    
	if position < 0 or position > len(katok) :
		print("데이터를 삽입할 범위를 벗어났습니다.")
		return
    
	katok.append(None)   # 빈칸 추가
	kLen = len(katok)       # 배열의 현재 크기

	for i in range(kLen-1, position, -1) :
		katok[i] = katok[i-1]
		katok[i-1] = None 

	katok[position] = friend   # 배열의 제일 뒤에 친구 추가


def delete_data(position) :  
    
	if position < 0 or position > len(katok) :
		print("데이터를 삭제할 범위를 벗어났습니다.")
		return

	kLen = len(katok)
	katok[position] = None	# 데이터 삭제
    
	for i in range(position+1, kLen) :
		katok[i-1] = katok[i]
		katok[i] = None	# 배열의 제일 위치 삭제

	del(katok[kLen-1])
    

## 전역 변수 선언 부분 ## 
katok = []
select = -1	# 1: 추가, 2: 삽입, 3: 삭제, 4: 종료


## 메인 코드 부분 ## 
if __name__ == "__main__" :
    
	while (select != 4) :

		select = int(input("선택하세요(1: 추가, 2: 삽입, 3: 삭제, 4: 종료)--> "))

		if (select == 1) :
			data = input("추가할 데이터--> ")
			add_data(data)
			print(katok)
		elif (select == 2) :
			pos = int(input("삽입할 위치--> "))
			data = input("추가할 데이터--> ")
			insert_data(pos, data)
			print(katok)
		elif (select == 3) :
			pos = int(input("삭제할 위치--> "))
			delete_data(pos)
			print(katok)
		elif (select == 4) :
			print(katok)
			exit
		else :
			print("1~4 중 하나를 입력하세요.")
			continue
```
# 데이터 추가 코드
```
def add_data(friend) :
	katok.append(None)
	kLen = len(katok)
	katok[kLen-1] = friend
```
매게변수로 받은 값을 리스트의 마지막에 추가하는코드로
`friend`로 받은 값을 `katok`리스트 마지막에 저장하기위해
`katok` 마지막에 빈값을 추가한다.
`kLen`변수로 `katok`의 길이를 저장한 다음
`katok[kLen-1] = friend`로 `kLen-1` 을 사용해 
`katok`리스트 마지막값을 가져오고 `friend`저장

# 데이터 삽입 코드
```
def insert_data(position, friend) :    
    
	if position < 0 or position > len(katok) :
		print("데이터를 삽입할 범위를 벗어났습니다.")
		return
    
	katok.append(None)   # 빈칸 추가
	kLen = len(katok)       # 배열의 현재 크기

	for i in range(kLen-1, position,-1) :
		katok[i] = katok[i-1]
		katok[i-1] = None 

	katok[position] = friend   # 배열의 제일 뒤에 친구 추가
```
매개변수로 `position,friend`로 전달받고
첫 `if` 문으로 삽입할 위치를 전달받는 `position`값이
0 보다 작거나 `katok`의 범위를 벋어날 경우를 잡아준다.
범위가 벗어자니 않은값이면 아래코드를 실행한다.
`katok`list 마지막에 빈값을 만들고 `kLen`에 길이를 저장
`for`문을돌면서 `katok`마지막 값에서 `postiton`번째까지의 값을
`katok[position]'에 'None'값이 올때까지 그 뒤에 값들을 뒤로 옮겨준다.
