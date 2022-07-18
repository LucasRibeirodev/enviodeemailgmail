import smtplib 
import email.message

def enviar_email(): 
  corpo_email = '''

  teste de envio de email

  '''
  msg = email.message.Message()
  msg['Subject'] = 'teste'
  msg['From'] = 'gestao.lucasribeiro@gmail.com'
  msg['To'] = 'lucas.dragoesmc@gmail.com'
  passoword = 'bbxvdnvbycubqyda'
  msg.add_header('Content-Type', 'text/html')
  msg.set_payload(corpo_email)

  s = smtplib.SMTP('smtp.gmail.com: 587')
  #smtp.smtp('smtp.gmail.com: 587')
  s.starttls()
  #credenciais de login
  s.login(msg['From'], passoword)
  s.sendmail(msg['From'],[msg['To']], msg.as_string().encode('utf-8'))

  print('Email Enviado!')
