# 使用 Vercel 反代 openai （图文教程）

## 简介

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
![阿里云域名注册](doc/2023-04-11-20-19-54.png)

## 部署

1. 点击一键部署按钮

   [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FLinLin00000000%2Fvercel-proxy-openai&project-name=vercel-proxy-openai&repository-name=vercel-proxy-openai&root-directory=src)

2. 用 Github 登录 Vercel，没有 Github 账户的去注册一个，网上很多教程就不展开了
![Vercel login](doc/2023-04-11-21-42-30.png)
3. 登录之后点击 Create 按钮
![Vercel create](doc/2023-04-11-21-42-47.png)
4. 接着等十几秒钟就创建好项目了，接下来进入仪表盘
![Vercel dashboard](doc/2023-04-11-21-42-57.png)
5. 进入到项目里之后，依次点击 Settings -> Domains，然后添加你的域名。添加的域名类型有两种，一种是一级域名(xxxx.com)和二级域名(openai.xxxx.com)，我个人推荐使用二级域名，因为一级域名一般用来做网站展示用，只能有一个，而二级域名可以有无限个（只要你有一个域名就可以自己创建无限个二级域名）
![Vercel domains](doc/2023-04-11-21-45-47.png)
6. 添加域名有三种方式，这里我们选第三种，因为简单
![Add Domain](doc/2023-04-11-21-47-17.png)
7. 接下来会分两种情况，分为一级域名和二级域名，都有教程，以阿里云为例（其他厂商也是差不多的配置，很简单的）

   1. 一级域名

      添加一级域名后 Vercel 会提示让你添加 DNS 解析记录
      ![DNS Config](doc/2023-04-11-21-47-57.png)
      在阿里云域名解析的解析设置里点击 添加记录，按照 Vercel 的提示配置好图中三个选项，点击确认
      ![DNS Set](doc/2023-04-11-21-48-21.png)
      回 Vercel 点击 Refresh 按钮，出现下图所示的情况就表明配置完成了
      ![Complete](doc/2023-04-11-21-48-38.png)
   2. 二级域名（以 openai 主机记录为例，可以改成自己喜欢的）

      添加二级域名后 Vercel 会提示让你添加 DNS 解析记录
      ![DNS Config](doc/2023-04-11-21-48-51.png)
      在阿里云域名解析的解析设置里点击 添加记录，按照 Vercel 的提示配置好图中三个选项，点击确认
      ![DNS Set](doc/2023-04-11-21-49-12.png)
      回 Vercel 点击 Refresh 按钮，出现下图所示的情况就表明配置完成了
      ![Complete](doc/2023-04-11-21-49-26.png)

🎉接下来就可以愉快地使用 openai api 啦~

有问题可以 [在此](https://github.com/LinLin00000000/vercel-proxy-openai/issues) 留言
