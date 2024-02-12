# python---data-science
Capstone project 
""" This programme is to create two different financial calculators. an investment calculator and a
 home repayment calculator"""

#user can chose investment or bond

import math
print('''
       INVESTMENT - to calculate the amount of interest you will earn on your investment OR
       BOND - to calculate the amount you will have to pay on a home loan''')


choice = str(input("enter either investment or bond from the menu above to proceed  \t"))
choice = choice.lower()
# if they chose investment ,they will be asked to chose simple interest or compound interest.
#calculation will be shown based on their selection

i = choice
if i == "investment":
   deposit_m = int(input("how much money do you want to deposit? "))
   interest_r = float(input("enter interest rate in percentage"))
   years_t= float(input("enter number of years you want to invest "))
   interest = input("would you like to know simple interest or compound interest\t")
   interest_r = float(interest_r/100)
   if interest == "simple interest":
         simple_interest = float(deposit_m*(1+interest_r*years_t))
         print(" simple interest is"+ str(simple_interest))
   else:
         compound_interest = float(deposit_m*math.pow((1+interest_r),years_t))
         print("compund interest is " + str(compound_interest))
#If they select bond, they will be asked to enter present value of the house, interest rate and numner 
        # of months, after calculation monthly payment will be printed. 
elif choice == "bond":
     choice = choice.lower()
     present_value = int(input("enter present value of the house: "))
     interest_rate = float(input("enter the interest rate: "))
     number_months = int(input("enter the number of months plan to repay the bond:"))
     interest_rate = float(interest_rate/100)
     repayment = float((interest_rate*present_value)/(1-(1+interest_rate)**(-number_months)))
     print(" user have to pay each month is " + str(repayment))
else:
     print("please chose the right choice")
      
