##YPC Random Damage



import random




damageMin = 0
damageMax = 0


def random_damage_midBias(damageMin, damageMax):
    global lst
    global damage
    lst = []
    count = 1
    entered = False



    while entered != True:
        try:
            damageMin = int(input("Enter the minimum for your range:\n\t"))
            damageMax = int(input("Enter the maximum for your range:\n\t"))
            entered = True
        except:
            print ("please enter a valid interger")

    first = damageMax // 3
    last = damageMax - first
    mid = damageMax // 2
    print (first, last, mid)


    for i in range (damageMin, damageMax):
        if i > first and i <= mid:
                count +=1
        if i < last and i > mid:
                count -=1
        if i > last:
            count = 1
            
        for j in range(0, count):
            lst.append(i)

        
    length = len(lst) 
    damageValue = random.randint(1, length)        
    damage = lst[damageValue]


random_damage_midBias(damageMin, damageMax)

print (lst)
print ("\n You Did:\t", damage, "damage")

