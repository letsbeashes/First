l = []
while True:
    list1 = [{"code": "1", "name": "computer", "brand": "sus", "cost": 124_000},
             {"code": "2", "name": "com", "brand": "a", "cost": 12_000},
             {"code": "3", "name": "ter", "brand": "as", "cost": 13_000},
             {"code": "4", "name": "coter", "brand": "us", "cost": 23_000}]

    chose = int(input("enter ur chose: "))
    if chose > 4 or chose < 1:
        print("invalid chose")
    elif chose == 1:
        member_ch = input("enter ur item: ")
        found = False
        for i in list1:
            if member_ch == i["code"]:
                l.append(i)
                print("ur item added.")
                found = True
        if not found:
            print("invalid item")

    elif chose == 2:
        if len(l) == 0:
            print("empty list")
        for item in l:
            print()
            for key, value in item.items():
                    print(f"{key}: {value}")

    elif chose == 3:
        if len(l) == 0:
            print("sry;there is nothing no remove!")
        choice =(input("enter your choice: "))
        f = False
        for items in l:
            if choice == items["code"]:
                l.remove(items)
                print("ur item removed.")
                f = True
        if not f:
            print("invalid item")
    elif chose == 4:
        print("thank you,have a nice day!")
        break
