
冒泡排序：
d0 = [2, 15, 5, 9, 7, 6, 4, 12, 5, 4, 2, 64, 5, 6, 4, 2, 3, 54, 45, 4, 44]
d0_out = [2, 2, 2, 3, 4, 4, 4, 4, 5, 5, 5, 6, 6, 7, 9, 12, 15, 44, 45, 54, 64]  # 正确排序

while 1:
    state = 0  # 假设本次循环没有改变
    for i in range(len(d0) - 1): #比较len(d0)-1次
        if d0[i] > d0[i + 1]:
            d0[i], d0[i + 1] = d0[i + 1], d0[i] #第i和第i+1个交换位置
            state = 1  # 有数值交换，那么状态值置1
    if not state:  # 如果没有数值交换，那么就跳出
        break

print(d0)
print(d0_out)

选择排序：
def select_sort(data): #设一个函数
    d1 = []
    while len(data): #循环语句
        min = [0, data[0]] #0跟第一个数比较 
        if min[1] > data[i]: #第二个数和date中的第0个数开始比较
             min = [i, data[i]] #比较
        del data[min[0]]  # 找到剩余部分的最小值，并且从原数组中删除
        d1.append(min[1])  # 在新数组中添加
    return d1

if __name__ == "__main__":
    d0 = [2, 15, 5, 9, 7, 6, 4, 12, 5, 4, 2, 64, 5, 6, 4, 2, 3, 54, 45, 4, 44]  # 原始乱序
    d0_out = [2, 2, 2, 3, 4, 4, 4, 4, 5, 5, 5, 6, 6, 7, 9, 12, 15, 44, 45, 54, 64]  # 正确排序
    d1 = select_sort(d0)
    print(d1)
    print(d0_out)

插入排序：
def direct_insertion_sort(d):   # 直接插入排序，因为要用到后面的希尔排序，所以转成function
    d1 = [d[0]]
    for i in d[1:]: #从第一个到最后一个
        state = 1
        for j in range(len(d1) - 1, -1, -1): #从len(d1)-1开始到倒数第一个，间隔-1
            if i >= d1[j]:
                d1.insert(j + 1, i)  # 将元素插入数组
                state = 0
                break
        if state:
            d1.insert(0, i) #在第一个位置插入数字
    return d1


if __name__ == "__main__":
    d0 = [2, 15, 5, 9, 7, 6, 4, 12, 5, 4, 2, 64, 5, 6, 4, 2, 3, 54, 45, 4, 44]  # 原始乱序
    d0_out = [2, 2, 2, 3, 4, 4, 4, 4, 5, 5, 5, 6, 6, 7, 9, 12, 15, 44, 45, 54, 64]  # 正确排序
    d1 = direct_insertion_sort(d0)
    print(d1)
    print(d0_out)
