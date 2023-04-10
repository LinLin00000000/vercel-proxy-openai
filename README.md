# 使用 Vercel 反代 openai （图文教程）

国内只是墙了 vercel 本身的域名，但是自定义域名没有墙，因此做了代理并绑定域名之后就可以用自己的域名在国内直连 openai api 了。

理论上也可以代理其他被墙的站点。

## 使用方法

- 访问 openai api 时，将 "api.openai.com" 换成你的自定义域名，例如

    ```javascript
    const host = 'YOUR DOMAIN'
    const url = `https://${host}/v1/chat/completions`
    ```

- 在其他 chatgpt 项目中，可以将变量 "OPENAI_API_BASE_URL" 设置为你的域名

## 要求

一个域名（无需备案），没有的话可以在阿里云上买一个几块钱一年的

## 部署

1. 点击一键部署按钮

   [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FLinLin00000000%2Fvercel-proxy-openai&project-name=vercel-proxy-openai&repository-name=vercel-proxy-openai&root-directory=vercel)

2. 部署成功之后进入到 vercel 的仪表盘，进入到你的项目里，依次点击 Settings -> Domains，然后添加你的域名。
   ![vercel dashboard](./doc/1.jpg)

   按照 vercel 的指引在域名解析添加记录，然后就可以愉快地使用 openai api 啦~
