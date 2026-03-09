from tkinter import *

root = Tk()
root.title("Обчислення")
root.geometry("350x300")

Label(text="Введіть перше число").pack()
entry1 = Entry()
entry1.pack()

Label(text="Введіть друге число").pack()
entry2 = Entry()
entry2.pack()

choice = IntVar()

Radiobutton(text="Сума (+)", variable=choice, value=1).pack()
Radiobutton(text="Різниця (-)", variable=choice, value=2).pack()
Radiobutton(text="Добуток (*)", variable=choice, value=3).pack()
Radiobutton(text="Частка (/)", variable=choice, value=4).pack()

result = Label(text="Результат:")
result.pack(pady=10)

def calculate():
    a = float(entry1.get())
    b = float(entry2.get())

    if choice.get() == 1:
        r = a + b
    elif choice.get() == 2:
        r = a - b
    elif choice.get() == 3:
        r = a * b
    elif choice.get() == 4:
        r = a / b

    result["text"] = "Результат: " + str(r)

Button(text="Обчислити", command=calculate).pack(pady=10)

root.mainloop()
