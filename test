import mysql.connector

mydb = mysql.connector.connect(
    user = 'ahmadrezaqh',
    host = 'localhost',
    password = 'ah#009/oogqh',
    database = 'school'
)
mycursor = mydb.cursor()

dict1 = {
    'agine' : 'True',
    'dict_name_and_password' : {
        'ahmadreza' : '1234', 
        'ali' : 'ali2'
    }
}
class School:
    def __init__(self):
        pass
    def Access(self, name, password):
        try:
            (print(f'welcome {name}'), dict1.update({'agine' : 'False'})) if dict1['dict_name_and_password'][name] == password else print('The password is incorrect')
        except KeyError as error:
            print(f'This {error} is incorrect')
    def Sing_up(self):
        try:
            sql = 'INSERT INTO students(st_name, st_lastname, st_age) VALUES(%s, %s, %s)'
            val = input('pleas enter name, lastname and age: ').strip().split()
            mycursor.execute(sql, val)
            mydb.commit()
        except mysql.connector.errors.ProgrammingError as error:
            print(error)
    def Searche(self):
        y_or_n = input('are you name index (y/n): ').lower()
        if y_or_n == 'y':
            sql = 'SELECT * FROM students WHERE st_id = %s'
            val = input('pleas enter index name: ').split()
            mycursor.execute(sql, val)
            result = mycursor.fetchall()
        elif y_or_n == 'n':
            sql = 'SELECT * FROM students WHERE st_name = %s OR st_lastname = %s'
            val = input('please enter name or lastname: ').strip().split()
            if len(val) != 2: val.append(' ')
            mycursor.execute(sql, val)
            result = mycursor.fetchall()
        for i in range(len(result)):
            # print(f'+-{'-' * len(str(result[i][0]))}-+-{'-' * len(result[i][1])}-+-{'-' * (result[i][2])}-+-{'-' * len(str(result[i][3]))}-+\n| {result[i][0]} | {result[i][1]} | {result[i][2]} | {result[i][3]} |\n+-{'-' * len(str(result[i][0]))}-+-{'-' * len(result[i][1])}-+-{'-' * len(result[i][2])}-+-{'-' * len(str(result[i][3]))}-+')
            print(result)
persone = School()
#list uptiens class
luc = [persone.Sing_up, persone.Searche]

#while for access
def access():
    while True:
        persone.Access( name= input('plaes enter the name: '), password= input('plaes enter the password: '))
        if dict1['agine'] == 'False': break
access()
#while for sing_up and seache
while True:
    try:
        questien = input('1- sing up\n2- searche\nplease enter the choice number: ')
        if questien == 'exit': break
        elif questien == 'bake': access()
        luc[int(questien) - 1]()
    except ValueError as error:
        print('pleas enter choice number! not text')
    except IndexError as error:
        print('please do not enter arbitrary values')
