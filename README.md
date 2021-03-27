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
msg.params.query = '테스트'; //#검색어
msg.params.display = "10" // #출력 뉴스 수
msg.params.sort = 'date' //#결과값의 정렬기준 시간순 date, 관련도 순 sim
msg.params.start = "1" //# 출력 위치

return msg;

```
## Sample flows
```json
[{"id":"309ddae6.03fa76","type":"function","z":"ef48714b.eb6b6","name":"네이버 뉴스 검색","func":"msg.params = {};\nmsg.params.query = '테스트'; //#검색어\nmsg.params.display = \"10\" // #출력 뉴스 수\nmsg.params.sort = 'date' //#결과값의 정렬기준 시간순 date, 관련도 순 sim\nmsg.params.start = \"1\" //# 출력 위치\n\nreturn msg;","outputs":1,"noerr":0,"initialize":"","finalize":"","x":350,"y":80,"wires":[["71f26e2f.5f20b"]]},{"id":"56070e01.ef0fa","type":"inject","z":"ef48714b.eb6b6","name":"","props":[{"p":"payload"},{"p":"topic","vt":"str"}],"repeat":"","crontab":"02 07 * * *","once":false,"onceDelay":0.1,"topic":"","payload":"","payloadType":"date","x":150,"y":80,"wires":[["309ddae6.03fa76"]]},{"id":"71f26e2f.5f20b","type":"navernews","z":"ef48714b.eb6b6","name":"","query":"","display":"","sort":"","start":"","creds":"a130dbf5.052c68","x":550,"y":80,"wires":[["3d9f9f70.34965"]]},{"id":"3d9f9f70.34965","type":"debug","z":"ef48714b.eb6b6","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"payload","targetType":"msg","statusVal":"","statusType":"auto","x":730,"y":80,"wires":[]},{"id":"a130dbf5.052c68","type":"naverNewsApiKey","name":"news key"}]
```
