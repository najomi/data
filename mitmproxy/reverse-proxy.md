Запустить reverse-proxy к домену для отладки запросов:

```sh
mitmproxy -R https://ya.ru/ --setheader :~q:Host:ya.ru -p 8081
```
