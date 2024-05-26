# Level1:
  Chacker@talking-web~level1:~$ curl 127.0.0.1 80

# Level2:
  nc 127.0.0.1 80
  GET / HTTP/1.0

# Level3:
  ipython

  In [1]: import requests

In [2]: requests.get("http://127.0.0.1/80")
Out[2]: <Response [200]>

In [3]: requests.get("http://127.0.0.1/")
Out[3]: <Response [200]>

In [4]: response = requests.get("http://127.0.0.1/80")

In [5]: response.read

---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
Cell In[5], line 1
----> 1 response.read

AttributeError: 'Response' object has no attribute 'read'

In [6]: response.text
Out[6]: 'pwn.college{0dn91ZUT__I884bC_C_2AlcuzAI.dBzNyMDL4gTN2UzW}\n'

# Level4:

hacker@talking-web~level4:~$ curl -H 'host: 91b17394657936a95b696abb1f0c25cc' http://127.0.0.1
pwn.college{UvLTe_HChefnQO8UL7d-QfRpNBF.dFzNyMDL4gTN2UzW}
  
