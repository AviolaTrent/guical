# guical
#It is a Calculator using GUI
#CALCULATOR

from tkinter import *

root = Tk()
root.geometry("620x360")
root.title("TRAV'S CALCULATOR")

def calculate():
    try:
        num1 = float(txt_num1.get())
        num2 = float(txt_num2.get())

        if operator == '+':
            res = num1 + num2
        elif operator == '-':
            res = num1 - num2
        elif operator == '*':
            res = num1 * num2
        elif operator == '/':
            res = num1 / num2

        lbl_result.config(text="Result: " + str(res))
    except ValueError:
        lbl_result.config(text="Invalid input")

def clear():
    txt_num1.delete(0, END)
    txt_num2.delete(0, END)
    lbl_result.config(text="Result: ")
    
 

def set_operator_plus():
    global operator
    operator = '+'

def set_operator_minus():
    global operator
    operator = '-'

def set_operator_multiply():
    global operator
    operator = '*'

def set_operator_divide():
    global operator
    operator = '/'





#variables
lbl_op = Label(root, text="|| __CHOOSE AN OPERATOR :)__ ||", bg="cyan", font=("arial", 11, "bold", "italic" ))





lbl_num1 = Label(root, text="[__Enter Number 1__] :", bg="grey", font=("arial", 11, "bold"))
txt_num1 = Entry(root)


lbl_num2 = Label(root, text="[__Enter Number 2__] :", bg="grey", font=("arial", 11, "bold"))
txt_num2 = Entry(root)

btn_plus = Button(root, text="Add[+]", command=set_operator_plus, bg="red", font=("arial", 11, "bold", "italic"))
btn_minus = Button(root, text="Subract[-]", command=set_operator_minus, bg="yellow green", font=("arial", 11, "bold", "italic"))
btn_multiply = Button(root, text="Multiply[*]", command=set_operator_multiply, bg="orange", font=("arial", 11, "bold", "italic"))
btn_divide = Button(root, text="Divide[/]", command=set_operator_divide, bg="magenta", font=("arial", 11, "bold", "italic"))



btn_calculate = Button(root, text="Calculate", command=calculate, bg="sky blue", font=("arial", 11, "bold"))
btn_clear = Button(root, text="Clear", bg="sky blue", command=clear, font=("arial", 11, "bold" ))

lbl_result = Label(root, text="Result: ", bg="cyan", font=("arial", 11, "bold", "italic"))


#GRID

lbl_op.grid(row=2, column=0, columnspan=4, sticky=EW)

lbl_num1.grid(row=1, column=0)
txt_num1.grid(row=1, column=1)

lbl_num2.grid(row=1, column=2)
txt_num2.grid(row=1, column=3)

btn_plus.grid(row=4, column=0, sticky=EW)
btn_minus.grid(row=4, column=1, sticky=EW)
btn_multiply.grid(row=4, column=2, sticky=EW)
btn_divide.grid(row=4, column=3, sticky=EW)

btn_calculate.grid(row=5, column=0, columnspan=2, rowspan=2,  sticky=EW)
btn_clear.grid(row=5, column=2, columnspan=2, rowspan=2, sticky=EW)

lbl_result.grid(row=7, column=0, columnspan=4)

root.mainloop()
