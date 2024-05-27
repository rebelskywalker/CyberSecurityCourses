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

# Level 13 curl to send arg
```
$ curl "http://127.0.0.1:80?a=af29d0f51496dc03035a068
40616168f"
```
# Level 14 nc to send arg
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

# Level 15 python to send arg
```
import requests
headers = "?a=620f7565a543aefb2f88b887217128e8"
url = 'http://127.0.0.1'
port = 80
url = f'{url}:{port}{headers}'
r = requests.get(url)
print(r.text)
```

# Level 16 curl to send mult args
```
hacker@talking-web~level16:~$ curl "http://127.0.0.1:80/?a=e1caa37e2f832758909d626dbc76c3da&b=4aec09fb%208f453401%261856f4f7%232bb2096e"
```

# Level 17 nc to send mult args
```
hacker@talking-web~level17:~$ nc 127.0.0.1 80
GET /?a=7365aaf97e648151e36a95d1f213ce63&b=66675b29%20ff006681%26251f1073%2378b722
Host: 127.0.0.1
Connection: close
```
# Level 18 pythong to send mult args
```
hacker@talking-web~level18:~$ /bin/python /home/hacker/Intro_to_Cybersecurity/level18.py
```

# Level 19 curl to url encode
```
hacker@talking-web~level19:~$ curl -d "a=516dc1a4a50cbfa7e53d29c83bcac259" 127.0.0.1:80
```

# Level 20 url encode with nc
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
# Level 21 url encode with python
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

# Level 22 url inline encoding
```
hacker@talking-web~level22:~$ curl -d "a=71e050f6fb089ed72b0d276cad7f262d&b=e94cbd83%2014d639f8%261dae2ba5%232a6a9282" 127.0.0.1:80
```

# Level 23 url incline encoding
```
hacker@talking-web~level23:~$ nc 127.0.0.1 80
POST / HTTP/1.1
Host: 127.0.0.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 78

a=ed6005c0dce51d18108a9a5732ac9d01&b=be5ede9c%2025cad8e2%264e5b09e1%2316d43944
HTTP/1.1 200 OK
Server: Werkzeug/3.0.3 Python/3.8.10
Date: Mon, 27 May 2024 06:44:35 GMT
Content-Length: 58
Server: pwn.college
Connection: close
```
# Level 24 multiple form data via python
```
import requests

p1 = "5b5b38b526292021b532279d28792167" 
p2 = "e68eb9f3 87bf26b9&26412b61#9eaaefb1"
params = {'a': p1, 'b': p2}
headers = {'Content-Type': 'application/x-www-form-urlencoded'}
url = 'http://127.0.0.1'
port = 80
# Correctly construct the URL with port number
url_with_port = f'{url}:{port}/'
r = requests.post(url_with_port, data=params, headers=headers)
print(r.text)
```

# Level 25 curl to submit json
Notes:
-X specifies request command to use, -H is to pass a header, -d is to include format data.
```
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{"a": "152e4b0869a2d21378769e9dce935251"}' \
  http://127.0.0.1:80

```

# Level 26 submit JSON using netcat
Using nc
Notice that for content length we must include every character in the form data payload and then also be aware of two more characters (\r \n) for the CRLF.
```
$ nc 127.0.0.1 80
POST / HTTP/1.1
Host: 127.0.0.1
Content-Type: application/json
Content-Length: 43

{"a": "d686f7422cbd7b7d42c07ab963e01ae4"}
```
Using echo
```
$ echo -e "POST / HTTP/1.1\r\nHost: 127.0.0.1\r\nContent-Type: application/json\r\nContent-Length: 41\r\n\r\n{\"a\": \"d686f7422cbd7b7d42c07ab963e01ae4\"}" | nc 127.0.0.1 80
```

# Level 27 python to submist JSON
```
import requests
url = 'http://127.0.0.1:80/' # http with port
load = {'a': '3d762725539d617135f8f737253760b3'}

headers = {'Content-Type': 'application/json'}
response = requests.post(url, json=load, headers=headers)
print(response.text)
```

# Level 28 
```
$ curl -X POST http://127.0.0.1:80 -H 'Content-Type: ap
plication/json' -d '{ "a": "2b7dab418c9a4e0704aef520aee3ab1e", "b": { "c": "8005f9f
4", "d": ["35a4aff6", "fec5db7b ab862559&d80867fd#92254593"] } }'
```

# Level 29
Note: lengths 117 and 116 worked. We used a python len counter to count the characters this time enclosing the whole string of key:values in quotes. this returned 17 and we had to escape each inner occurrence of quotes.
```
echo "{\"a\":\"31fab7fd132757857d2bb57c5f2c0f02\",\"b\":{\"c\":\"d9c1367a\",\"d\":[\"b82e1a20\",\"959485c8 3855f0df&4f43d5db#68e48409\"]}}" | wc -c
```

** ANSWER **

```
$ echo -e "POST / HTTP/1.1\r\nHost: 127.0.0.1\r\nContent-Type: application/json\r\nContent-Length: 116\r\n\r\n{\"a\":\"31fab7fd132757857d2
bb57c5f2c0f02\",\"b\":{\"c\":\"d9c1367a\",\"d\":[\"b82e1a20\",\"959485c8 3855f0df&4
f43d5db#68e48409\"]}}" | nc 127.0.0.1 80
```

# Level 30
```
import requests

url = 'http://127.0.0.1:80'
payload = {
    "a": "9924bb65adfa87136feb597f50017007",
    "b": {
        "c": "c9e6d7b1",
        "d": ["d285297f", "39ba17dc 5dfb7d53&34cba762#b9d6afa1"]
    }
}
headers = {'Content-Type': 'application/json'}

response = requests.post(url, json=payload, headers=headers)

print(response.text)
```

# Level 31
Needs -L option for following links
```
$ curl -X GET 127.0.0.1:80 
<!doctype html>
<html lang=en>
<title>Redirecting...</title>
<h1>Redirecting...</h1>
<p>You should be redirected automatically to the target URL: <a href="/7e5e8a6be5baa1eb0408a40815fe0f19">/7e5e8a6be5baa1eb0408a40815fe0f19</a>. If not, click the link.
```
```
$ curl -L -X GET 127.0.0.1:80 
pwn.college{8bK8eWN6ujsb_V2_mAM5_Ag6xyy.dhTOyMDL4gTN2UzW}
```

# Level 32

# Level 33

# Level 34

# Level 35

# Level 36

# Level 37

# Level 38

# Level 39

