# loan_calculator_3-4
#loan_calculator_3/4 stage

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
    print("It will take " + str(z // 12) + " years and " + str(z % 12) + " months to repay this loan!")
