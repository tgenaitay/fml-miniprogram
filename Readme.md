# Background & objectives
Today we will dive into the basics of the mini-program framework and try to understand what's going on. The main assignment of the day is to build a copycat of **["FML: your every day life stories"](http://www.fmylife.com/)**, check it out now.

**Day objectives:**

- Master the WeChat IDE.
- Understand the config.
- Play with the view/logic layers.
- Discover the framework.


**Exercise objectives:**

- MP configuration.
- Display a list of FML "stories".
- Setup, fetch and persist remote data using Leancloud.
- Post a FML.
- Upvote a FML.

Example:

![](asset/new-fml.gif)


## 1. Setup

**Get your development environment:**

- Install the [IDE](https://github.com/apelegri/wechat-miniprogram-whitebook#wechat-ide) and read the tutorial.
- Create a mini-program project within the IDE (we will provide the AppID necessary to create a project).
- Add the *Quickstarter* source code in the folder
- **Init git**, push it to a Github repo


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

Here is a section of our manual to help you to [configure your MP](https://github.com/apelegri/wechat-miniprogram-whitebook#core-setup-of-your-mp).

**Further resources:**

- WeChat official [documentation](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/config.html)

## 3. Create dynamic pages

In this step you will start to use the core principles of the framework. We recommend that you read this part of the [manual](https://github.com/apelegri/wechat-miniprogram-whitebook#create-dynamic-pages) before you start.

**Specs**

- Create a **list of cards** to display your FML stories on the **index.wxml**.
- Bring out your designer skills and add **wxcss** classes.
- Use *data binding* methods to get data from your **index.js** file

**Further suggestions:**

- [WXML / HTML differences](https://github.com/apelegri/wechat-miniprogram-whitebook#wxml---html-whats-the-deal) you need to know.
- [FML cards](http://www.fmylife.com/) are ugly: you can surely do better.

## 4. Leancloud DB

The goal here is to **fetch the data** from Leancloud. You will need to build a new DB, named **FML-MP DB**, and use it to inject content into the cards you created ;)


**Specs**

- Sign up to [Leancloud](leancloud.cn). It's free.
- Create your FML DB within Leancloud.
- Setup Leancloud in your MP.
- Fetch data from Leancloud (FML) and bind data in your cards.

Here is a [tutorial](https://github.com/apelegri/wechat-miniprogram-whitebook#leancloud-db) that **should be helpful.**

**Further resources:**

- Leancloud mini-program [setup](https://leancloud.cn/docs/weapp.html).
- Leancloud data storage [guide](https://leancloud.cn/docs/leanstorage_guide-js.html).


## 5. Submit a new FML

Now, it is time to **create a new page** which allow users to submit a FML.

**Specs**

- Create a new page to submit a FML.
- Post the data collected from the form (.wxml) to the logical layer (.js) then to Leancloud.

Everything is in the [tutorial](https://github.com/apelegri/wechat-miniprogram-doc#leancloud-db) just follow it.

**Further resources:**

- Leancloud mini-program [setup](https://leancloud.cn/docs/weapp.html).
- Leancloud data storage [guide](https://leancloud.cn/docs/leanstorage_guide-js.html).


## 6. Upvote

Here is the tricky part: create a counter which allows users to upvote a FML story.

**Specs**

- Add a new column in your Leancloud table to store the number of **upvotes**.
- Each time a user taps on the upvote icon or btn, increment the counter.
- Post the update to Leancloud.

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


