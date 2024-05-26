# Level1: Curl access uri and port
```
  Chacker@talking-web~level1:~$ curl 127.0.0.1 80
```
# Level2:
```
  $ nc 127.0.0.1 80
  $ GET / HTTP/1.0
```
# Level3:
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



# LEvel 6
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
# Level 11 

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

# Level 12


