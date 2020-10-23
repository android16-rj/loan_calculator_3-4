#: loan_calculator_3-4
#:loan_calculator_3/4 stage

import math

que_1 = input("""What do you want to calculate? 
type "n" for number of monthly payments,
type "a" for annuity monthly payment amount,
type "p" for loan principal: """)

if que_1 == "n":
    a = int(input("Enter the loan principal: "))
    b = int(input("Enter the monthly payment: "))
    c = int(input("Enter the loan interest: "))
    i = c / (12 * 100)
    z = (math.ceil(math.log(b / (b - (i * a)), (1 + float(i)))))
    if z % 12 == 0:
        print("It will take " + str(z // 12) + " years to repay this loan!")
    elif z // 12 == 1:
        print("It will take " + str(z // 12) + " year and " + str(z % 12) + " months to repay this loan!")
    elif z // 12 == 1 and z % 12 == 0:
        print("It will take " + str(z // 12) + " year to repay this loan!")
    elif z < 12:
        print("It will take " + str(z) + " months to repay this loan!")
    elif z == 1:
        print("It will take " + str(z) + "month to repay this loan!")
    else:
        print("It will take " + str(z // 12) + " years and " + str(z % 12) + " months to repay this loan!")

#: for 2nd part

if que_1 == "a":
    a = int(input("Enter the loan principal: "))
    b = int(input("Enter the number of periods: "))
    c = float(input("Enter the loan interest: "))
    i = c / (12 * 100)
    z = (math.ceil(a * (i * (1 + i) ** b) / (((1 + i) ** b) - 1)))
    print(f'Your monthly payment = {z}!')

#:for 3rd part

if que_1 == "p":
    a = float(input("Enter the annuity payment: "))
    b = int(input("Enter the number of periods: "))
    c = float(input("Enter the loan interest: "))
    i = c / (12 * 100)
    z = (round(a / ((i * (1 + i) ** b) / (((1 + i) ** b) - 1))))
    print(i)
    print(f'Your loan principal = {z}!')
