# WeChat mini-program challenge

Build a simple mini-program in 1 day.

## Background & objectives

Today we will discover the basics of the mini-program framework. The main assignment is to build a copycat of **["FML: your every day life stories"](http://www.fmylife.com/)**, check it out now.

**Day objectives:**

- Master the WeChat MP Integrated Development Environment.
- Understand the config of Mini-programs.
- Play with the view/logic layers.
- Discover the framework components and APIs.

**Exercise objectives:**

- Setup your workstation
- Setup the MP.
- Display a list of user-generated content (FML "stories")
- Setup, fetch and persist remote data using Leancloud.
- Post a user-generated content.
- Update content.

See it yourself:

![](asset/new-fml.gif)


## 1. Setup

**Get your development environment:**

- Install the [IDE](https://github.com/apelegri/wechat-miniprogram-wiki#wechat-ide) and read the quick tutorial provided.
- Create a mini-program project within the IDE (your teacher will provide the MP **AppID** necessary to create a project).
- Add the *Quickstart* source code in the folder
- **Init git**, commit and push it to your own Github repo
- *If you are not able to **preview** your MP, ask help from a teacher*


## 2. Mini-program configuration

The WeChat framework allows to configure **five items:**

- Routing
- Window
- Tab bar
- Network timeout (not used here)
- Debug  (not used here)

**Specs**

The `app.json` file is where to start your mini-program:

- Create your routes using `pages`.
- Style your `window`.
- Generate your `tabBar`.

Here is a section of our manual to help you to [configure your MP](https://github.com/apelegri/wechat-miniprogram-wiki#core-setup-of-your-mp).

**Further resources:**

- WeChat official [documentation](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/config.html)

## 3. Create dynamic pages

In this step you will start to use the core principles of the framework. We recommend that you read this part of the [manual](https://github.com/apelegri/wechat-miniprogram-wiki#create-dynamic-pages) before you start.

**Specs**

- Create a **list of cards** to display your FML stories on the **index.wxml**.
- Bring out your designer skills and add **wxcss** classes.
- Use *data binding* methods to get data from your **index.js** file

**Further suggestions:**

- [WXML / HTML differences](https://github.com/apelegri/wechat-miniprogram-wiki#wxml---html-whats-the-deal) you need to know.
- [FML cards](http://www.fmylife.com/) are ugly: you can surely do better!

## 4. Leancloud DB

The goal here is to **fetch the data** from Leancloud. You will need to use a shared cloud DB, named **FML-miniprogram**, and use it to inject content into the cards you created ;)


**Specs**

- Sign up to [Leancloud](leancloud.cn). It's free.
- Don't forget to verify your email address.
- Send your username to a teacher: you will be added to the *wagon-alumni* team and will then get access to the **FML-miniprogram** app on Leancloud
- Setup Leancloud in your MP. [Read this](https://github.com/apelegri/wechat-miniprogram-wiki#2-install-and-initialize-leancloud).
- Fetch data from the shared DB (**FML-miniprogram**) and bind data in your cards.
Here is a [tutorial](https://github.com/apelegri/wechat-miniprogram-wiki#leancloud-db) that **should be helpful.**

**Further resources:**

- Leancloud mini-program [setup](https://leancloud.cn/docs/weapp.html).
- Leancloud data storage [guide](https://leancloud.cn/docs/leanstorage_guide-js.html).


## 5. Submit a new FML

Now, it is time to **create a new page** which allows users to submit a FML story!

**Specs**

- Create a new page to submit a FML.
- Post the data collected from the form (.wxml) to the logical layer (.js) then to Leancloud.

Everything is in the [tutorial](https://github.com/apelegri/wechat-miniprogram-wiki#leancloud-db) just follow it.

**Further resources:**

- Leancloud mini-program [setup](https://leancloud.cn/docs/weapp.html).
- Leancloud data storage [guide](https://leancloud.cn/docs/leanstorage_guide-js.html).


## 6. Upvote (optional)

Here is a bit of challenge: create a counter which allows users to upvote a FML story.

**Specs**

- The Leancloud DB has an **upvotes** column
- Each time a user taps on the upvote icon or btn, increment the counter.
- *Post* the update to Leancloud.

**Further suggestions & resources:**


Divide the work in **three steps:**

1. Get the object ID of the FML clicked by user.
2. Persist updated data to Leancloud DB:

	- Increment counter
	- Persist data in the DB
3. Update local data:
	- Find the object ID in the local data storage
	- Increment counter and update local data.

- Leancloud documentation on [Object possibilities](https://leancloud.github.io/javascript-sdk/docs/AV.Object.html).
- WeChat official [documentation](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/event.html).
- Leancloud mini-program [Github repository](https://github.com/leancloud/leantodo-weapp).


