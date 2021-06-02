# SMART CALCULATOR

A calculator is a machine which allows people to do math operations more easily. For example, most calculators will add, subtract, multiply, and divide. Some also do square roots, and more complex calculators can help with calculus and draw function graphs.

This calculator is built using Tkinter.

This calculator can perform addition, subtraction, multiplication, division, can find hcf, lcm, remainder and modulus.
Give this calculator a try!

### To install tkinter from pypi:
`pip install tkintertable`

## CODE:
```python
from tkinter import *

def add(a,b):
    return a + b

def sub(a,b):
    return a - b

def mul(a,b):
    return a * b

def div(a,b):
    return a / b

def mod(a,b):
    return a % b

def lcm(a,b):
    L = a if a>b else b
    while L <= a*b:
        if L%a == 0 and L%b == 0:
            return L
        L+=1

def hcf(a,b):
    H = a if a<b else b
    while H >= 1:
        if a%H == 0 and b%H == 0:
            return H
        H-=1

def extraxt_from_text(text):
    l = []
    for t in text.split(' '):
        try:
            l.append(float(t))
        except ValueError:
            pass
    return l

def calculate():
    text = textin.get()
    for word in text.split(' '):
        if word.upper() in operations.keys():
            try:
                l = extraxt_from_text(text)
                r = operations[word.upper()](l[0] , l[1])
                list.delete(0,END)
                list.insert(END,r)
            except:
                list.delete(0,END)
                list.insert(END,'Something went wrong please enter again')
            finally:
                break
        elif word.upper() not in operations.keys():
            list.delete(0,END)
            list.insert(END,'Something went wrong please enter again')

operations = {'ADD':add , 'ADDITION':add , 'SUM':add , 'PLUS':add ,
                'SUB':sub , 'DIFFERENCE':sub , 'MINUS':sub , 'SUBTRACT':sub,
                 'LCM':lcm , 'HCF':hcf , 'PRODUCT':mul , 'MULTIPLICATION':mul, 'MUL':mul,
                 'MULTIPLY':mul , 'DIVISION':div , 'DIV':div ,'DIVIDE':div, 'MOD':mod ,
                  'REMANDER':mod , 'MODULUS':mod}

win = Tk()
win.geometry('450x300')
win.title('Smart Pugger')
win.configure(bg='lightskyblue')

l1 = Label(win , text='I am a smart calculator.',width=20 , padx=3)
l1.place(x=150,y=10)
l2 = Label(win , text='My name is Pugger!' , padx=3)
l2.place(x=165,y=60)
l3 = Label(win , text='How can i help you?' , padx=3)
l3.place(x=165,y=110)

textin = StringVar()
e1 = Entry(win , width=30 , textvariable = textin)
e1.place(x=125,y=160)

b1 = Button(win , text='Just this' ,command=calculate)
b1.place(x=190,y=190)

list = Listbox(win,width=20,height=3)
list.place(x=155,y=230)

win.mainloop()
```
## SAMPLE OUTPUTS:

![output-1](https://user-images.githubusercontent.com/81489001/120550355-60f42300-c412-11eb-8209-7dd1239df9bb.PNG)

![output-2](https://user-images.githubusercontent.com/81489001/120550372-66516d80-c412-11eb-9b1e-a992a68fbd6c.PNG)

![output-3](https://user-images.githubusercontent.com/81489001/120550388-6cdfe500-c412-11eb-9b8e-41618ce4c212.PNG)

![output-4](https://user-images.githubusercontent.com/81489001/120550400-723d2f80-c412-11eb-8971-90cb31ecd406.PNG)
