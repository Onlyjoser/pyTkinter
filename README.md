# pyTkinter
Tkinter é a interface padrão do Python para criação de GUI. [Leia mais](https://docs.python.org/3/library/tkinter.html)

Configuração "Default" do Tkinter.
```py
from tkinter import *

programa = Tk()
programa.title("Meu projeto no Tkinter")   # Nome do programa
programa.geometry("300x350")    # Tamanho do programa (LarguraxAltura
programa.configure(background="#f1f1f1")    # Cor de fundo do programa
programa.resizable(False, False)    # Deixar a pessoa modificar o tamanho do programa


programa.mainloop()
