# Lem.py
The  first  program
def funprint ():
    print('        显示功能界面：')
    print('..........................')
    print('1.添加学员')
    print('2.删除学员')
    print('3.修改学员')
    print('4.查询学员')
    print('5.显示所有学员')
    print('6.退出系统')
    print('..........................')
info=[]
def fun_add():
    new_id = input('请输入学号')
    new_name = input('请输入姓名')
    new_phone = input('请输入手机号')

    global info
    for i in info:
        if new_name==i['name']:
            print('该用户已经存在')
            return
    info_dict = {}

    info_dict['id']=new_id
    info_dict['name']= new_name
    info_dict['phone']= new_phone
    info.append(info_dict)
    print(info)

def fun_delete():
    find_name = input('请输入查找的学员')
    global info
    for i in info:
        if find_name==i['name']:
            info.remove(i)
            break
    else:
        print('该学员不存在')
    print(info)
def fun_revision():
    find_name=input('请输入修改学员姓名：')
    global  info
    for i in info:
        if find_name==i['name']:
            i['phone']=input('请输入新的手机号')
            break
    else:
        print('用户不存在')
    print(info)
def fun_find():
    global info
    find_name=input('请输入查询学员姓名：')
    for i in info:
        if find_name==i['name']:
            print('查询信息如下：.....')
            print(f"学员学号是{i['id']},姓名是{i['name']},手机号是{i['phone']}")
            break
    else:
        print('该用户不存在')
def fun_print():
    global info
    print('学号\t  姓名\t  手机号\t')
    for i in info:
        print(f"{i['id']}\t{i['name']}\t{i['phone']}")
while True:        #主函数
    funprint()

    fun_num = int (input('请输入功能序号：'))
    if fun_num ==1:
        fun_add()
        print('添加学员成功')
    elif fun_num==2:
        print('删除学员成功')
        fun_delete()
    elif fun_num==3:
        fun_revision()
        print('修改学员成功')
    elif fun_num==4:
        fun_find()
        print('查询学员成功')
    elif fun_num==5:
        fun_print()
    elif fun_num==6:
        exit_num=input('是否退出程序？yes or no')
        if exit_num=='yes':
            break
    else:
        print('输入错误')
