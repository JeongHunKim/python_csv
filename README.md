# python_csv
import csv
import re

f=open("D:/kjh/0408/gihu2.csv")
main_data = csv.reader(f)
print(main_data)

temp=[]
for idx,row in enumerate(main_data):
    temp.append(row)
f.close()

temp1=[]
for idx,row in enumerate(temp[8:]):
    temp1.append(row)
b=0.0
i=0
for idx,row in enumerate(temp1):
    try:
        if row[4]:
            if b<float(row[4]):
                b=float(row[4])
                i=idx
    except Exception as e:
        print('Index : {0}\nError : {1}\nList : {2}'.format(idx, e, temp1[idx]))
print("최고기온 : %.2f" %b)
print(temp1[i])
print(__name__)
