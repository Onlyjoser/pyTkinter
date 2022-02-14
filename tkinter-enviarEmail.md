# Código para enviar emails usando o Tkinter
O código conta com algumas importações, as bibliotecas são, **tkinter**, **EmailMessage**, **smtplib**.

```py
from tkinter import *
from email.message import EmailMessage
import smtplib

programa = Tk()
programa.title("Envia Emails")   # Nome do programa
programa.geometry("300x350")    # Tamanho do programa (LarguraxAltura
programa.configure(background="#f1f1f1")    # Cor de fundo do programa
programa.resizable(False, False)    # Deixar a pessoa modificar o tamanho do programa

def enviaEmails():
    emailUsuario = vEmail.get()
    emailMensagem = vMensagem.get("1.0", END)
    emailAssunto = vAssunto.get()
    emailAlvo = vEmailAlvo.get()
    print('Email enviado.')

    msg = EmailMessage()
    msg['Subject'] = emailAssunto
    msg['From'] = emailUsuario
    msg['To'] = emailAlvo
    msg.set_content(emailMensagem)

    with smtplib.SMTP_SSL('smtp.gmail.com', 465) as smtp:
        smtp.login(emailUsuario, 'Senha do seu email aqui.')
        smtp.send_message(msg)

#   Colocar o email
Label(programa, text='E-mail', anchor=W).place(x=10, y=13, width=100, height=20)
vEmail=Entry(programa)
vEmail.place(x=10, y=30, width=170, height=20)

#   Colocar o email do alvo
Label(programa, text='Email do alvo', anchor=W).place(x=10, y=55, width=100, height=20)
vEmailAlvo=Entry(programa)
vEmailAlvo.place(x=10, y=73, width=170, height=20)

#   Colocar o assunto
Label(programa, text='Assunto', anchor=W).place(x=185, y=13, width=60, height=20)
vAssunto=Entry(programa)
vAssunto.place(x=185, y=30, width=90, height=20)

#   Colocar a mensagem do email
Label(programa, text='Mensagem', anchor=W).place(x=10, y=120, width=100, height=20)
vMensagem=Text(programa)
vMensagem.place(x=10, y=150, width=280, height=100)

#   Botão
Button(programa, text='Enviar', command=enviaEmails, padx=50, pady=25, bd=4).place(x=75, y=250)

programa.mainloop()
```

# Resultado
![Screenshot_11](https://user-images.githubusercontent.com/95121360/153883648-e536a1ba-4eee-4aaf-bd0b-cf6c7ca69fdd.png)
