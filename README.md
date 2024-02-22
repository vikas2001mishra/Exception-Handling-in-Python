# Exception-Handling-in-Python 

# Exception Handling:
              Syntax error
              Runtime error



# SyntaxError:

x = 20
if x == 20      #SyntaxError:here missing (:) after 20
    print('The value of x is:',x)
import logging


# Runtime error

print(20/0)  #ZeroDivisionError:


# TypeError:

print(10/'a')              #TypeError: unsupported operand type(s) for /: 'int' and 'str'


# ValueError:

x = int(input("Enter some number:"))
print(x)     #if enter albhabet number for example a,b,c,d..etc. then output..
               #ValueError: invalid literal for int() with base 10: 'r'





# What is an exception ?
       An Unwanted and Unexpected event which is going to disturb our regular flow of the program.


# What is the meaning of exception handling ?
         Defining alternative way to continue rest of the program normally.



try:
    statement 1
except:
    statement 2



'''try:
    print('read data from the nagpur server')
except:
    print('read data from delhi')'''



# If exception handling is not there then Python terminate the program abnormally, print exeception error message



print('Hello')
print(20/0)
print("Hii")    #ZeroDivisionError: division by zero



'''print('Hello')
try:
    print(20/0)
except:
    print("Hii")'''  # Now our program run without any error bacause we used to try: & except:




print('Hello')
try:
    print(20/3)
except:
    print("Hii")
print('hii error')

import os
print(os.getcwd())
print(![](main.py))





'''try:
    print('Outer try block')
    try:
        ('Inner try block')
        print(20/0)
    except:
        print('Error occured')
        print('Inner Except block')
    print('Statement2')
except:
    print('Outer Except block')
print('Statement3')'''







try:
    print('Statement1')
    print(10/0)
except:
    print('statement2')
finally:
    print('staement3')





'''try:
    print('Statement1')
    print(10 / 5)
except:
    print('statement2')
finally:
    print('staement3')'''




# Else Statement


try:
    print('try')
    print(10/0)
except:
    print('can not divide by 0')
else:
    print('Calculation completed successfully')
finally:
    print('the job ends')




'''try:
    print('try')
    print(10/2)
except:
    print('can not divide by 0')
else:
    print('Calculation completed successfully')
finally:
    print('the job ends')'''






try:
    print('try')
except:
    print('except')





'''try:
    print('try')
finally:
    print('finally')'''



# Case 1

try:
    print('Try')
except:
    print('Except')
finally:
    print('Finally')



# Case 2
# Without try only except block is invalid

except:
    print('Except')'''




# Case 3
# invalid

else:
    print('Hello')



# Case 4
# invalid

finally:
    print('finally')


# Case 5
# Valid

try:
    print("Hii")
except:
    print("Hello")

    

# Case 6
# Valid


try:
    print("HII")
finally:
    print("HELLO")



# Case 7
# Valid
try:
    print('try')
except:
    print('except')
else:
    print('else')]



# Case 8
# Invalid


try:
    print('try')
else:
    print('else')'''



# Case 9
# Invalid


try:
    print('try')
else:
    print('else')
finally:
    print('finally')

# Case 10
# valid


try:
    print('try')
except ZeroDivisionError:
    print('except1')
except TypeError:
    print('except2')



# Case 11
# Invalid


try:
    print('try')
except ZeroDivisionError:
    print('except1')
elif:
    print('else1')
else:
    print('else2')




# Case 12
# Invalid
try:
    print('try')
except:
    print('except')
finally:
    print('finally1')
finally:
     print('finally2')




# Case 13
# Invalid
# Can't write any statement between try and except


try:
    print('try')
print('hello')
except:
      print('Except')





# Case 14
# Invalid


try:
    print('try')
except ZeroDivisionError:
    print('except1')
print('hello')
except TypeError:
       print('except2')


       


# Types of Exceptions---
    1.Predefined exceptions/inbuilt exceptions
    2.Userdefined exceptions/customized exceptions




class TooYoungException(Exception):
    def __init__(self,args):
        self.msg = args
class TooOldException(Exception):
    def __init__(self,args):
        self.msg = args
age = int(input("Enter Your Age:"))
if age>60:
    raise TooOldException('Plz do not see this movie')
elif age<18:
    raise TooYoungException("You are see this movie")
else:
    print("Your ticket is confirmed")





'''result = None
x = int(input('Number 1:'))
y = int(input('Number 2:'))
try:
    result = x/y
except:
    print("Error in your code")
print("Result",result)'''





'''class TeaException(Exception):
    def __init__(self,args):
        self.msg = args
    temp = 1
    if temp == 0:
        raise TeaException("It's too cold to drink")
    else:
        print('You have can your tea')'''




# Logging Priority Levels
           CRITICAL - 50 -   serious problems that needs high attention
           ERROR - 40 - Problem is serious but not that much critical
           WARNING - 30 - caution must be required,alert to the programmer
           INFO - 20 - message with some important information
           DEBUG - 10 - with debuging information
           NOTSET - 0 - Logging level not set





# How to Implemented
    Need to create the file to store the messeges
    Level messeges


import logging
logging.basicConfig(filename= 'log.txt',level=logging.DEBUG)
print('Python Logging Demo')
logging.debug('This is debug a message')
logging.info('This is info a message')
logging.error('This is error a message')
logging.warning('This is warning a message')
logging.critical('This is critical a message')




'''logging.basicConfig(filename= 'log.txt',level=logging.DEBUG)
logging.info('A new request came')
try:
    x = int(input('Enter First number:'))
    y = int(input('Enter Second number:'))
    print(x/y)
except ZeroDivisionError as e:
    print('can not divide with zero')
    logging.exception(e)
except ValueError as e:
    print('Enter only int value')
    logging.exception(e)
logging.info('Request processing completed')'''






''''try:
    enter_age = int(input('Enter the age of the customer:'))
    if enter_age < 18:
        raise TooYoungException
    elif enter_age > 60:
        raise TooOldException
    else:
        print('Your ticket is confirmed')

except TooYoungException:
    print('Your age is too less to see the movie')
    print()

except TooOldException:
    print('Your age is too high to see the movie')
    print()

else:
    print('Enjoy the movie')

finally:
    print('Your transaction is completed, have a nice day')'''






try:
    result = 0
    x = int(input('Enter the number: '))
    y = int(input('Enter the number: '))
    print(result)
    result = x/y
    print(result)
except Exception as e:
    if str(e) == "division by zero":
        print('its zero')
    else:
        print('Some other error')
else:
    print('The new result is: ', result)
finally:
    print('The job completed...')














