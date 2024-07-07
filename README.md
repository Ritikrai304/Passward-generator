# Passward-generator
from tkinter import *
import string
import random
root = Tk()
root.geometry("400x350")
root.title("Password Generator By RITIK")

def generator():
    small_alphabets = string.ascii_lowercase
    capital_alphabets = string.ascii_uppercase
    numbers = string.digits
    special_chareters = string.punctuation

    all = small_alphabets+capital_alphabets+numbers+special_chareters
    password_lengt=int(length_box.get())

    if choice.get()==1:
        passwordbox.insert(0, random.sample(small_alphabets, password_length))

    if choice.get()==2:
        passwordbox.insert(0, random.sample(small_alphabets+capital_alphabets, password_length))

    if choice.get()==3:
        passwordbox.insert(0, random.sample(all, password_length))

root.config(bg="grey")
choice=IntVar()

label = Label(root, text="Password Generator", font = "bold", bg="grey", fg="white")
label.grid()

weakradiobutton = Radiobutton(root, text="Weak", value=1,variable=choice, font="bold")
weakradiobutton.grid(pady=5,padx=10)

mediumradiobutton = Radiobutton(root, text="Medium", value=2,variable=choice, font="bold")
mediumradiobutton.grid(pady=5)

Strongradiobutton = Radiobutton(root, text="Strong", value=3,variable=choice, font="bold")
Strongradiobutton.grid(pady=5)
 

label = Label(root, text="Password Length", font="bold", bg="grey", fg="white" )
label.grid(pady=10)

length_box = Spinbox(root, from_=5,to_=18,width=5, font="bold")
length_box.grid()

generatebutton = Button(root, text="Generate", font="bold", command=generator)
generatebutton.grid(pady=5)

passwordbox = Entry(root, width= 25, bd=2 , font="bold")
passwordbox.grid(padx=50)
root.mainloop()
