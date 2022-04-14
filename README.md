# Random-Damage
Algorithm for calculating random damage figures in a given range. 
##YPC Random Damage



import random




damageMin = 0
damageMax = 0


def random_damage_midBias(damageMin, damageMax):
    global lst
    global damage
    lst = []
    count = 1
    first = damageMax // 3
    last = damageMax - first
    mid = damageMax // 2
    entered = False


    while entered != True:
        try:
            damageMin = int(input("Enter the minimum for your range:\n\t"))
            damageMax = int(input("Enter the maximum for your range:\n\t"))
            entered = True
        except:
            print ("please enter a valid interger")
            

    lowRange = damageMin
    highRange = damageMax
    damageValue = random.randint(lowRange, highRange)

    
    for i in range(damageMin, damageMax):
        if i > first and i < last:
            if i <= mid:
                count +=1
            elif i > mid:
                count -=1

        if count == last or i > last or i <= first:
            count = 1
                
        for j in range(count):  
            lst.append(i)

            
    damage = lst[damageValue]


random_damage_midBias(damageMin, damageMax)

print (lst)
print ("\n You Did:\t", damage)
