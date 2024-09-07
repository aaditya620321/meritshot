# meritshot
python code


import time as t
user_pin = 1234
user_balance = 1234565432.97
user_name = "Mr.Nirbikar"
print("Welcome to your bank account", user_name, end = "\n\n")
choice = 9
while(True):
    print("\t\t0. Logout and Exit") 
    print("\t\t1. View Account Balance")
    print("\t\t2. Deposit Cash")
    print("\t\t3. Withdraw The cash")
    print("\t\t4. Deposit Cash" )
    print("\t\t5. Change Pin")
    print("\t\t6. Return CARD")
    print("\t\t7.Choose the language")
    choice = int(input("Enter number to proceed >"))
    print("\n\n")
    if choice == 0:
        print("Exiting...")
        t.sleep(2)
        print("You have been logged Out from the application")
        break
    elif choice in (1,2,3,4,5):
        num_of_tries = 3
        while(num_of_tries !=0):
            input_pin= int(input("Please enter the 4 digit pin >"))

            if input_pin == user_pin:
                print("Account authorized! \n\n")

                if choice ==1:
                    print("Loading Account Balance...")
                    t.sleep(1.5)
                    print("Your current balance is Rs.", user_balance, end = "\n""\n""\n")
                    break
                
                elif choice ==2:
                    print("Opening Cash Withdrawl..")
                    t.sleep(1.5)

                    while(True):
                        withdraw_amt = int(input("Enter the amount you wish to withdraw >"))

                        if withdraw_amt>user_balance:
                            print("Can't withdraw Rs.", withdraw_amt)
                            print("Please enter a lower amount!")
                            continue
                        else:
                            print("withdrawing Rs.",withdraw_amt)
                            confirm = input("Confirm ? Y/N > ")
                            if confirm in ('Y','y'):
                                user_balance-=withdraw_amt
                                print("Amount withdrawn - Rs.", withdraw_amt)
                                print("Remaining balance - Rs.", user_balance, end = "\n\n\n")
                                break
                            else:
                                print("Cancelling transaction...")
                                t.sleep(1)
                                print("Transaction Cancelled!\n\n")
                                break
                    break
                elif choice ==3:
                    print("Loading Cash Deposit....")
                    t.sleep(1.5)

                    deposit_amt = int(input("Enter the amount you wish to deposit > "))
                    print("Depositing Rs.", deposit_amt)
                    confirm = input("Confirm ? Y/N >")
                    if confirm in  ('Y', 'y'):
                        user_balance+=deposit_amt
                        print("Amount deposited - Rs.",deposit_amt)
                        print("updated balance - Rs.", user_balance,end= "\n\n\n")
                    else:
                        print("Cancelling transaction...")
                        t.sleep(1)
                        print("Transaction Cancelled!\n\n")

                    break
                elif choice ==4:
                    print("Loading PIN Change...")
                    t.sleep(1.5)
                    pin_new = float(input("Enter your new PIN >"))

                    print("Changing PIN to", pin_new)
                    confirm = input("Confirm ? Y/N > ")
                    if confirm in ('Y', 'y'):
                        user_pin = pin_new
                        print("PIN changed successfully! \n\n")
                    else:
                        print("Cancelling PIN Change...")
                        t.sleep(1)
                        print("Process cancelled! \n\n")
                    break

                           








