# wxdevtool

WeChat WebDevTool in Docker(With LXDE)

## Run

```bash
docker run -d --name wxdevtool -p 8080:80 -v /path/to/projects:/projects seancheung/wxdevtool:latest
```

## Commands

```bash
docker exec -t wxdevtool wxdevtool help
```

## Tags

|  Tag   |   Version    |
| :----: | :----------: |
| latest |    latest    |
|  1.02  | 1.02.1902010 |

### RC Tags

rc tags are automated images which are not configured yet. To config manullay:

1. Pull an RC image

```bash
docker pull seancheung/wxdevtool:1.02-rc
```

2. Run

```bash
docker run -d --name wxdevtool-rc -p 8080:80 seancheung/wxdevtool:1.02-rc
```

3. Config Wine

```bash
docker exec -t wxdevtool-rc winecfg
```

Open Browser at _http://localhost:8080_, follow wine's instructions in UI. The attached shell will automatically quit when done.

4. Config wxdevtool to enable IDE service port

```bash
docker exec -t wxdevtool-rc wxdevtool start
```

Open Browser at _http://localhost:8080_, Open Wechat WebDevTool's settings and enable IDE service port. See [Referece](https://developers.weixin.qq.com/miniprogram/dev/devtools/cli.html)

### Custom build Args

**WXURL**

https://servicewechat.com/wxa-dev-logic/download_redirect?type=x64&from=mpwiki

> Always fetch the latest

**NODE_URL**

https://nodejs.org/dist/v${version}/node-v${version}-linux-x64.tar.gz

Mirror:

https://npm.taobao.org/mirrors/node/v${version}/node-v${version}-linux-x64.tar.gz

**NWJS_URL**

https://dl.nwjs.io/v${version}/nwjs-sdk-v${version}-linux-x64.tar.gz

Mirror:

https://npm.taobao.org/mirrors/nwjs/v${version}/nwjs-sdk-v${version}-linux-x64.tar.gz
