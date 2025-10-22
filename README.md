# 11
lermontov
f = open("28129_B.txt")
s = f.readlines()
m71 = 0
m72 = 0
m1 = 0
m2 = 0
max1 = 0
max2 = 0
for i in range(len(s)):
    x = int(s[i])
    if x % 7 == 0 and x % 160 == m71 % 160 and x > m71:
        m71 = x
    elif x % 7 == 0 and x % 160 != m71 % 160 and x > m71:
        m72 = m71
        m71 = x
    elif (x % 7 == 0) and (x % 160 != m71 % 160) and (x > m72):
        m72 = x
    elif x % 7 != 0 and x % 160 == m1 % 160 and x > m1:
        m1 = x
    elif x % 7 != 0 and x % 160 != m1 % 160 and x > m1:
        m2 = m1
        m1 = x
    elif x % 7 != 0 and x % 160 != m1 % 160 and x > m2:
        m2 = x
if m71 == 0 and m72 == 0:
    print(0, 0)
elif (m72 == 0) and (m2 == 0) and (m71 % 160 == m1 % 160):
    print(0, 0)
else:
    if (m71 + m72) > (max1 + max2):
        max1 = m71
        max2 = m72
    if ((m71 + m1) > (max1 + max2)) and (m71 % 160 != m1 % 160):
        max1 = m71
        max2 = m1
    if ((m71+m2)>(max1+max2)) and (m71 % 160 != m2 % 160):
        max1 = m71
        max2 = m2
    if (((m72 + m1) > (max1 + max2)) and ((m72 % 160) != (m1 % 160))):
        max1 = m72
        max2 = m1
    print(max1, max2)
