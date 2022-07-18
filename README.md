# enviodeemailgmail
enviar email pelo gmail
#enviar email pelo gmail

import smtplib
import email.message

def enviar_email():
    corpo_email = '''<p> teste de envio de email</p>'''
    
    msg = email.message.Message()
    msg['Subject'] = 'titulo do email'
    msg['From'] = 'remetente'
    msg['To'] = 'destinatario'
    passoword = 'senha do email do remetente'
    msg.add.header('Content-Type', 'text/html')
    msg.set_payload(corpo_email)
    
    s = smtp.SMTP('smtp.gmail.com: 587')
    s.starttls()
    #credenciais de login
    s.login(msg['From'], passoword)
    s.sendmail(msg['From'],[msg['To']], msg.as_string().encode('utf-8'))
    
    print('Email Enviado!')
