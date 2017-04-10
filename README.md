# python
 reptile
#python爬虫，爬取网页
#coding=utf-8
from bs4 import BeautifulSoup
import lxml  
import urllib
from urllib import request
url = 'http://ecpi.ggj.gov.cn/jndfgz/'#
req=request.Request(url)
res=urllib.request.urlopen(req)
cont=res.read()
soup = BeautifulSoup(cont,'html.parser')  

for link in soup.center.find_all('a'):
    if 'href' in link.arrts:
        print (link.attrs['href'])
