node-red-contrib-navernews
================

Node-RED node for navernews



## Install

To install the stable version use the `Menu - Manage palette - Install`
option and search for node-red-contrib-navernews, or run the following
command in your Node-RED user directory, typically `~/.node-red`

    npm install node-red-contrib-navernews

## Wrapper naver news  API  
- https://developers.naver.com/docs/search/news/

## Sample parameters
```js

msg.url = 'https://openapi.naver.com/v1/search/news.json';

msg.params = {};
msg.params.query = 'AA' //검색어
msg.params.display = '10' //출력 뉴스 수
msg.params.sort = 'date'//결과값의 정렬기준 시간순 date, 관련도 순 sim
msg.params.start = '1' //출력 위치

return msg;
```

## Sample flows
```json

```
