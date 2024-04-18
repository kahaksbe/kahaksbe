# @tppt6
import requests
import random
import os
# = = = = = = = = = = = = 

Z = '\033[1;31m' #احمر
X = '\033[1;33m' #اصفر
Z1 = '\033[2;31m' #احمر ثاني
F = '\033[2;32m' #اخضر
A = '\033[2;34m'#ازرق
C = '\033[2;35m' #وردي
B = '\033[1;36m'#سمائي
Y = '\033[1;34m' #ازرق فاتح

# = = = = = = = = = = = =
h = 0
g = 0
import pyfiglet
ll = pyfiglet.figlet_format('R E X')
print(B+ll)
rt = requests.session()
litters = 'qwertyuiopasdfghjklzxcvbnm1234567890'
u = ''

id = input("[+] Id : ")

token = input("[+] Token : ")
l=B+ll
print('')
hea = {
        'accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'accept-encoding': 'gzip, deflate, br',
        'accept-language': 'en-US,en;q=0.9,ar;q=0.8',
        'cache-control': 'max-age=0',
        'sec-ch-ua': '" Not;A Brand";v="99", "Google Chrome";v="91", "Chromium";v="91"',
        'sec-ch-ua-mobile': '?0',
        'sec-fetch-dest': 'document',
        'sec-fetch-mode': 'navigate',
        'sec-fetch-site': 'same-origin',
        'sec-fetch-user': '?1',
        'upgrade-insecure-requests': '1',
        'user-agent': 'Mozilla/5.0(Windows NT 10.0;Win64;x64) AppleWebKit/537.36(KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36'
    }
while True:
	user = str("".join(random.choice(litters)for x in range(4)))
	tiko = f'https://www.tiktok.com/@{user}?'
	reqsnd = rt.get(tiko, headers=hea).status_code
	if reqsnd == 404:
	        g+=1
	        os.system('cls' if os.name == 'nt' else 'clear')
	        print(f'{l}\n[=] Hit : {g}\n[=] Bad : {h}\n[=] User : {user}')
	        bot = f"https://api.telegram.org/bot{token}/sendMessage?chat_id={id}&text=𝗛𝗘𝗟𝗟𝗢 𝗡𝗘𝗪 𝗨𝗦𝗘𝗥 𝗧𝗜𝗞 𝗧𝗢𝗞\n= = = = = = = = = = = = = \n[=] 𝗨𝗦𝗘𝗥 : {user}\n= = = = = = = = = = = = = \n[=] 𝗕𝗬 : @ww8wwww | @ayqjl "
	        rt.get(bot)
	else:
		 h+=1
		 os.system('cls' if os.name == 'nt' else 'clear')
		 print(f'{l}\n[=] Hit : {g}\n[=] Bad : {h}\n[=] User : {user}')
