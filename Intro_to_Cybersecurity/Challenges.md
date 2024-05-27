# Level1: Curl access uri and port
```
  Chacker@talking-web~level1:~$ curl 127.0.0.1 80
```
# Level2: netcat get request
```
  $ nc 127.0.0.1 80
  $ GET / HTTP/1.0
```
# Level3: python to write get request
```
  ipython
  import requests
  requests.get("http://127.0.0.1/80")
  Out[2]: <Response [200]>
  requests.get("http://127.0.0.1/")
  Out[3]: <Response [200]>
  response = requests.get("http://127.0.0.1/80")
  response.text
  Out[6]: 'pwn.college{0dn91ZUT__I884bC_C_2AlcuzAI.dBzNyMDL4gTN2UzW}\n'
```

# Level4: Curl change host
```
$ curl -H 'host: 91b17394657936a95b696abb1f0c25cc' http://127.0.0.1
pwn.college{UvLTe_HChefnQO8UL7d-QfRpNBF.dFzNyMDL4gTN2UzW}
```

# Level 5



# LEvel 6 python change host name
```
import requests
headers = {'host': "9c4a144aecd0b411009a1cb633881bc0"}
url = 'http://127.0.0.1'
port = 80
url = f'{url}:{port}'
r = requests.get(url, headers=headers)
print(r.text)
```

# Level 7 Curl to change path
```
hacker@talking-web~level7:~$ curl http://127.0.0.1//90452535bde5123cc609a5877b83452e
pwn.college{QDiJHaudRazcwESw7Sdl00L6-OF.dRzNyMDL4gTN2UzW}
hacker@talking-web~level7:~$ curl http://127.0.0.1:80/90452535bde5123cc609a5877b83452e
pwn.college{QDiJHaudRazcwESw7Sdl00L6-OF.dRzNyMDL4gTN2UzW}
```
# Level 8 net cat to change path
```
hacker@talking-web~level8:~$ printf "GET /3d7eabe77ccc11c1446e1557966c8a0d HTTP/1.1\r\nHost: 127.0.0.1\r\nConn
ection: close\r\n\r\n" | nc 127.0.0.1 80
HTTP/1.1 200 OK
Server: Werkzeug/3.0.3 Python/3.8.10
Date: Sun, 26 May 2024 09:11:36 GMT
Content-Length: 58
Server: pwn.college
Connection: close

pwn.college{gP-2m0vwZaWX1PFhs-byljnZEgx.dVzNyMDL4gTN2UzW}
```


# Level 9 python to change path
```
import requests
headers = "/8735bd87507622dd2ba8fac3b6c0b59e"
url = 'http://127.0.0.1'
port = 80
url = f'{url}:{port}{headers}'
r = requests.get(url)
print(r.text)
```

# Level 10 encode special character or space path
```
hacker@talking-web~level10:~$ curl 127.0.0.1:80/a5425217%20b32904af/ac212716%202b93
3b1e
pwn.college{cIzsKNbRuK1SzLASkHBxw1MwOgq.ddzNyMDL4gTN2UzW}
```
# Level 11 use netcat for encoding

NOTE: Printf did not work !!! had to use echo. All my earlier netcat answers in this section worked with printf to my knowledge.

```
hacker@talking-web~level11:~$ echo -e "GET /dfc06abd%20e86d7a5e/72c63140%20c9b401
94 HTTP/1.0\r\nHost: 127.0.0.1\r\nConnection: close\r\n\r\n" | nc 127.0.0.1 80
HTTP/1.1 200 OK
Server: Werkzeug/3.0.3 Python/3.8.10
Date: Sun, 26 May 2024 21:54:16 GMT
Content-Length: 58
Server: pwn.college
Connection: close

pwn.college{ITL0CHo3ty4SmxkMm0UyQ0Vu_YB.dhzNyMDL4gTN2UzW}
```

ANSWER Using nc, and hitting enter appropriately once or twice to simular CRLFs
```
$ nc 127.0.0.1 80
GET /dfc06abd%20e86d7a5e/72c63140%20c9b40194 HTTP/1.0
Host: 127.0.0.1
Connection: close
```

# Level 12 use python for encoding
```
import requests
headers = "/d44d0ae4%20c5fbef7c/000df879%2096603bfe"
url = 'http://127.0.0.1'
port = 80
url = f'{url}:{port}{headers}'
r = requests.get(url)
print(r.text)
```

# Level 13 
```
$ curl "http://127.0.0.1:80?a=af29d0f51496dc03035a068
40616168f"
```
# Level 14
```
nc 127.0.0.1 80
GET /?a=c1bb0692f91f3fe8ca9f2f6a82ffbd03 HTTP/1.1    
Host: 127.0.0.1
Connection: close

HTTP/1.1 200 OK
Server: Werkzeug/3.0.3 Python/3.8.10
Date: Sun, 26 May 2024 23:25:30 GMT
Content-Length: 58
Server: pwn.college
Connection: close
```

# Level 15
```
import requests
headers = "?a=620f7565a543aefb2f88b887217128e8"
url = 'http://127.0.0.1'
port = 80
url = f'{url}:{port}{headers}'
r = requests.get(url)
print(r.text)
```

# Level 16
```
hacker@talking-web~level16:~$ curl "http://127.0.0.1:80/?a=e1caa37e2f832758909d626dbc76c3da&b=4aec09fb%208f453401%261856f4f7%232bb2096e"
```

# Level 17
```
hacker@talking-web~level17:~$ nc 127.0.0.1 80
GET /?a=7365aaf97e648151e36a95d1f213ce63&b=66675b29%20ff006681%26251f1073%2378b722
Host: 127.0.0.1
Connection: close
```
# Level 18
```
hacker@talking-web~level18:~$ /bin/python /home/hacker/Intro_to_Cybersecurity/level18.py
```

# Level 19
```
hacker@talking-web~level19:~$ curl -d "a=516dc1a4a50cbfa7e53d29c83bcac259" 127.0.0.1:80
```

# Level 20
```
hacker@talking-web~level20:~$ nc 127.0.0.1 80
POST / HTTP/1.1
Host: 127.0.0.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 34

a=875f6ea63ab35fc759fdec7302bbc8e6
HTTP/1.1 200 OK
Server: Werkzeug/3.0.3 Python/3.8.10
Date: Mon, 27 May 2024 00:36:54 GMT
Content-Length: 58
Server: pwn.college
Connection: close

pwn.college{M01_UZRD9fgwYRf-6B1YG8sZDms.ddDOyMDL4gTN2UzW}
```
# Level 21
```
import requests

p1 = "a3efe64ef440a3ef5c4304882f4e7b6a"
params = {'a': p1}
headers = {'Content-Type': 'application/x-www-form-urlencoded'}
url = 'http://127.0.0.1'
port = 80
# Correctly construct the URL with port number
url_with_port = f'{url}:{port}/'
r = requests.post(url_with_port, data=params, headers=headers)
print(r.text)

```
