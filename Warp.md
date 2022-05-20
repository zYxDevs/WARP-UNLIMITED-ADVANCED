# Script Code
----
***Without Telegram Logger***<br>
``WARP_ID`` Enter your WARP/WARP+ ID<br>
```
import urllib.request
import json
import datetime
import random
import string
import time
import os
import sys
os.system("title UnlimitedWrapUsage")
os.system('cls' if os.name == 'nt' else 'clear')
print ("Script by Dr.Caduceus")
referrer = input("[#] Enter the WARP/WARP+ ID: ")
def genString(stringLength):
	try:
		letters = string.ascii_letters + string.digits
		return ''.join(random.choice(letters) for i in range(stringLength))
	except Exception as error:
		print(error)
def digitString(stringLength):
	try:
		digit = string.digits
		return ''.join((random.choice(digit) for i in range(stringLength)))
	except Exception as error:
		print(error)
url = f'https://api.cloudflareclient.com/v0a{digitString(3)}/reg'
def run():
	try:
		install_id = genString(22)
		body = {"key": "{}=".format(genString(43)),
				"install_id": install_id,
				"fcm_token": "{}:APA91b{}".format(install_id, genString(134)),
				"referrer": referrer,
				"warp_enabled": False,
				"tos": datetime.datetime.now().isoformat()[:-3] + "+02:00",
				"type": "Android",
				"locale": "es_ES"}
		data = json.dumps(body).encode('utf8')
		headers = {'Content-Type': 'application/json; charset=UTF-8',
					'Host': 'api.cloudflareclient.com',
					'Connection': 'Keep-Alive',
					'Accept-Encoding': 'gzip',
					'User-Agent': 'okhttp/3.12.1'
					}
		req         = urllib.request.Request(url, data, headers)
		response    = urllib.request.urlopen(req)
		status_code = response.getcode()
		return status_code
	except Exception as error:
		print("")
		print("[×] Error:", error)

g = 0
b = 0
while True:
	os.system('cls' if os.name == 'nt' else 'clear')
	animation = ["[■□□□□□□□□□] 10%","[■■□□□□□□□□] 20%", "[■■■□□□□□□□] 30%", "[■■■■□□□□□□] 40%", "[■■■■■□□□□□] 50%", "[■■■■■■□□□□] 60%", "[■■■■■■■□□□] 70%", "[■■■■■■■■□□] 80%", "[■■■■■■■■■□] 90%", "[■■■■■■■■■■] 100%"] 
	for i in range(len(animation)):
		time.sleep(0.2)
		sys.stdout.write("\r[∆] Progress: " + animation[i % len(animation)])
		sys.stdout.flush()
	result = run()
	if result == 200:
		g += 1
		print(f"\n[•] WARP+ ID: {referrer}")
		print(f"[✓] Added: {g} GB")
		print(f"[#] Total: {g} Good {b} Bad")
		for i in range(10,-1,-1):
			sys.stdout.write(f"\033[1K\r[!] Cooldown: {i} seconds")
			sys.stdout.flush()
			time.sleep(1)
# Cooldown Timer should be 10 Second
# Good = Success / Bad = Fail
	else:
		b += 1
		print(f"[#] Total: {g} Good {b} Bad")
		for i in range(10,-1,-1):
			sys.stdout.write(f"\033[1K\r[!] Cooldown: {i} seconds")
			sys.stdout.flush()
			time.sleep(1)
  ```
***With Telegram Logger***<br>
``WARP_ID`` Enter your WARP/WARP+ ID.<br>
``BOT_API_TOKEN`` Telegram Bot Token from BotFather.<br>
``CHANNEL_ID`` Channel ID or Group ID like @example or @mychannel to which log needs to be send. Channel or Group should be public.
  ```
  import urllib.request
import json
import datetime
import random
import string
import time
import os
import sys
WARP_ID = input("[#] Enter the WARP/WARP+ ID: ")
BOT_API_KEY = input("Enter Bot Token.")
CHANNEL_ID = input("Enter Channel ID.")
SEND_LOG = "1" # 0 to Disable
def genString(stringLength):
  try:
    letters = string.ascii_letters + string.digits
    return ''.join(random.choice(letters) for i in range(stringLength))
  except Exception as error:
    print(error)
def digitString(stringLength):
  try:
    digit = string.digits
    return ''.join((random.choice(digit) for i in range(stringLength)))
  except Exception as error:
    print(error)
url = f'https://api.cloudflareclient.com/v0a{digitString(3)}/reg'
def run():
  try:
    install_id = genString(22)
    body = {"key": "{}=".format(genString(43)),
        "install_id": install_id,
        "fcm_token": "{}:APA91b{}".format(install_id, genString(134)),
        "WARP_ID": WARP_ID,
        "warp_enabled": False,
        "tos": datetime.datetime.now().isoformat()[:-3] + "+02:00",
        "type": "Android",
        "locale": "es_ES"}
    data = json.dumps(body).encode('utf8')
    headers = {'Content-Type': 'application/json; charset=UTF-8',
          'Host': 'api.cloudflareclient.com',
          'Connection': 'Keep-Alive',
          'Accept-Encoding': 'gzip',
          'User-Agent': 'okhttp/3.12.1'
          }
    req         = urllib.request.Request(url, data, headers)
    response    = urllib.request.urlopen(req)
    status_code = response.getcode()
    return status_code
  except Exception as error:
    print("")
    print("[×] Error:", error)
g = 0
b = 0
while True:
  os.system('cls' if os.name == 'nt' else 'clear')
  animation = ["[■□□□□□□□□□] 10%","[■■□□□□□□□□] 20%", "[■■■□□□□□□□] 30%", "[■■■■□□□□□□] 40%", "[■■■■■□□□□□] 50%", "[■■■■■■□□□□] 60%", "[■■■■■■■□□□] 70%", "[■■■■■■■■□□] 80%", "[■■■■■■■■■□] 90%", "[■■■■■■■■■■] 100%"] 
  for i in range(len(animation)):
    time.sleep(0.2)
    sys.stdout.write("\r[∆] Progress: " + animation[i % len(animation)])
    sys.stdout.flush()
  result = run()
  if result == 200:
    g += 1
    if send_msg == "1":
        urllib.request.urlopen("https://api.telegram.org/bot"+ BOT_API_KEY + "/sendMessage?chat_id=" + CHANNEL_ID + "&text=" + "WARP%20ID:%20" + WARP_ID + "%20DATA%20RECEIVED:%20" + str(g) + "GB%20FAILED%20ATTEMPTs:%20" + str(b))
    print(f"\n[•] WARP+ ID: {WARP_ID}")
    print(f"[✓] Added: {g} GB")
    print(f"[#] Total: {g} Good {b} Bad")
    for i in range(10,-1,-1):
      sys.stdout.write(f"\033[1K\r[!] Cooldown: {i} seconds")
      sys.stdout.flush()
      time.sleep(1)
  else:
    b += 1
    print(f"[#] Total: {g} Good {b} Bad")
    for i in range(10,-1,-1):
      sys.stdout.write(f"\033[1K\r[!] Cooldown: {i} seconds")
      sys.stdout.flush()
      time.sleep(1)
  ```
<b>Made with 💗 by Dr.Caduceus</b>
