# secreat_santa
import random
a=('Frank Grimes',
['Homer Simpson', 'Marge Simpson'],
['Carl Carlson', 'Lenny Leonard'],
'Bart Simpson',
'Lisa Simpson',
['Maude Flanders', 'Ned Flanders'])
#b=1,2,3,4,5,6
santa_list=[]
santa=[]
all_santa=[]

for i in a:
    if type(i)==list:        
        santa_list.append(i)
        all_santa.extend(i)
    else:
        all_santa.append(i)

unused_santa= all_santa
zz={}
b=all_santa.copy()
for people in b:
    for parnter in santa_list:
        if people in parnter:
            zz=parnter
            break
        else:
            zz={}
    if people in unused_santa:
        z= list(set(unused_santa)-{people}-set(zz))
        rand=random.choice(z)
        unused_santa.remove(rand)
    else:
        rand=random.choice(unused_santa)
        unused_santa.remove(rand)

    print(people,"->",rand)
