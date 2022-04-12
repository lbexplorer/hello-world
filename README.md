# hello-world
the first repository
import os





def main():
    path1 = os.getcwd()
    path2 = os.path.join(path1, "bank1")
    path3 = os.path.join(path1, "bank2")

    bank2_data = []
    f3 = []
    with open(path2, 'r') as file1:
        bank1_data1 = file1.readlines()
    with open(path3, 'r') as file2:

        list2 = file2.readlines()
        for i in list2:
            i = i.replace(' ', ',').split(',')
            temp = i[0]
            i[0] = i[1]
            i[1] = temp
            bank2_data.append(','.join(i))
    for i in bank1_data1:
        if i not in bank2_data:
            f3.append(i)
    for i in bank2_data:
        if i not in bank1_data1:
            f3.append(i)

    with open("result.txt", 'w') as file3:
        file3.writelines(f3)


if __name__ == '__main__':
    main()
