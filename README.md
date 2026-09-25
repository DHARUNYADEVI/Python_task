# Python Problem Solving
## Name: Dharunyadevi S
## Register Number: 212223220018

This repository contains Python solutions for 10 problem-solving questions based on arrays, strings, sliding window, prefix sum, sets, dictionaries, and intervals.

## Problems Covered

1. Student Attendance Analysis

   * Finds the longest continuous sequence without duplicate student IDs.
   * Concept: Sliding Window and Set
  ```py

a=list(map(int,input().split()))
left=0
maximum=0
seen=set()
for right in range(len(a)):
    while a[right] in seen:
        seen.remove(a[left])
        left+=1
    seen.add(a[right])
    maximum=max(maximum,right-left+1)
print(maximum)
```

2. Online Shopping Price Analysis

   * Finds the maximum sum of a continuous range.
   * Concept: Kadane's Algorithm
```py
a=list(map(int,input().split()))
current=a[0]
maximum=a[0]
for i in range(1,len(a)):
    current=max(a[i],current+a[i])
    maximum=max(maximum,current)
print(maximum)
```
3. Rainwater Collection System

   * Calculates the amount of water trapped between buildings.
   * Concept: Two Pointers
```py
a=list(map(int,input().split()))
left=0
right=len(a)-1
left_max=0
right_max=0
water=0
while left<right:
    if a[left]<=a[right]:
        if a[left]>=left_max:
            left_max=a[left]
        else:
            water+=left_max-a[left]
        left+=1
    else:
        if a[right]>=right_max:
            right_max=a[right]
        else:
            water+=right_max-a[right]
        right-=1
print("Trapped water: ",water)
```
4. Employee Performance Analysis

   * Finds the continuous period with the highest performance score.
   * Concept: Kadane's Algorithm
```py
a=list(map(int,input().split()))
current=a[0]
maximum=a[0]
for i in range(len(a)):
    current=max(a[i],current+a[i])
    maximum=max(maximum,current)
print(maximum)
```
5. Product Sales Analysis

   * Finds the maximum product of a continuous subarray.
   * Concept: Maximum Product Subarray
```py
a=list(map(int,input().split()))
minimum=a[0]
maximum=a[0]
answer=a[0]
for i in range(1,len(a)):
    x=a[i]
    if x<0:
        maximum,minimum=minimum,maximum
    maximum=max(x,x*maximum)
    minimum=min(x,x*minimum)
    answer=max(answer,maximum)
print(answer)
```
6. Customer Purchase History

   * Finds the longest sequence of unique product IDs.
   * Concept: Sliding Window and Set
```py
a=list(map(int,input().split()))
seen=set()
left=0
maximum=0
for right in range(len(a)):
    while a[right] in seen:
        seen.remove(a[left])
        left+=1
    seen.add(a[right])
    maximum=max(maximum,right-left+1)
print(maximum)
```
7. Bank Transaction Analysis

   * Counts continuous transaction groups that equal a target amount.
   * Concept: Prefix Sum and Dictionary
```py
a=list(map(int,input().split()))
target=int(input())
count=0
total=0
seen={0:1}
for x in a:
    total+=x
    if total-target in seen:
        count+=seen[total-target]
    seen[total]=seen.get(total,0)+1
print(count)
```
8. Employee Skill Grouping

   * Groups strings containing the same characters in different orders.
   * Concept: Anagram and Dictionary
```py
a = input().split()
groups = {}
for word in a:
    key = ''.join(sorted(word))
    if key not in groups:
        groups[key] = []
    groups[key].append(word)
for group in groups.values():
    print(*group)
```
9. Network Packet Analysis

   * Finds the longest sequence of consecutive numbers.
   * Concept: Set
```py
a = list(map(int, input().split()))
numbers = set(a)
maximum = 0
for x in numbers:
    if x - 1 not in numbers:
        current = x
        length = 1
        while current + 1 in numbers:
            current += 1
            length += 1
        maximum = max(maximum, length)
print(maximum)
```
10. Hospital Appointment Scheduling

* Merges overlapping appointment time ranges.
* Concept: Sorting and Intervals
```py
n = int(input())
intervals = []
for i in range(n):
    start, end = map(int, input().split())
    intervals.append([start, end])
intervals.sort()
result = []
for start, end in intervals:
    if not result or start > result[-1][1]:
        result.append([start, end])
    else:
        result[-1][1] = max(result[-1][1], end)
for start, end in result:
    print(start, end)
```
## Concepts Used

* Arrays
* Strings
* Sets
* Dictionaries
* Sliding Window
* Prefix Sum
* Kadane's Algorithm
* Two Pointers
* Sorting
* Intervals
* Maximum Product Subarray
* Anagram Grouping

## Language

Python 3

## Purpose

The purpose of this repository is to practice Python problem-solving and commonly used data structure and algorithm techniques.
## Output:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5779bd71-6ade-48eb-9620-0ab0d6d4dd62" />


