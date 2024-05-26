# Level1:
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

# Level4:
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


# Level 7
