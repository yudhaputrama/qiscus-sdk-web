
# Introduction

With Qiscus Chat SDK (Software Development Kit), You can embed chat feature
inside your application quickly and easily without dealing with complexity
of real-time comunication infrastructure. We provide Chat UI that has been
designed and optimized for easy customization. So, you can modify the UI to
show off your branding identity, favorite color, or customize event.

## A Brief About Chat

Talking about chat app, you may figure out such messenger app like Whatsapp. You
might have familiar with the flow, how to start conversation, and do things,
like sharing image inside chat room. If you want to create chat app, for
customer service, for instance, Qiscus Chat SDK enable you to establish chat UI
and functionalities easily. But before dive into it, there are essential basic
knowledges you need to know about chat app.

### 3 Basic Flow of Chat App

In a chat app, to start a conversation, we usually choose person we want to
chat with, from a contact list. Then, we start conversation inside a chat room.
In a chat room, we can do things such as sharing images, sending emoji, sharing
contact, location, and many more. We can even know when a person is typing
or when our message has been read. If chatting is done, we can go back to
conversation list which display our conversations in the app. To make a chat
app with the described flow, we noticed that the most complex part is creating
chat room, which posses many features inside it. Hence, Qiscus Chat SDK provide
an easy way to create chat app without dealing with complexity of real-time
comunication infrastructure that resides inside a chat room.

## Qiscus Chat SDK and UI Components

![Qiscus Chat SDK](https://cdn.rawgit.com/qiscus/qiscus-sdk-web/feature/docs/docs/images/intro01.png "Qiscus Chat SDK")

In spite or real-time chat, Qiscus Chat SDK provides UI that can be customized
according to your needs. But please keep in mind that, by default, Qiscus
provides UI for chat room only. If you need to create contact list and
conversation list UI, for example, you need to create it your own. However,
we provide essential data that you can get and utilize for your app.

## Qiscus Chat SDK Features

When you try our chat SDK, you will find the default built-in features such as:
- Private & group chat
- Typing indicator
- Delivery indicator
- Image and file attachment
- Online presence
- Read receipt
- Reply message
- Pending messages
- Emoji support

You also can access more advance and customizable features such as:
- Server side integration with Server API and Webhook
- Customize your user interface
- Embed bot engine in your app
- Enable push notification
- Export and import messages from your app

## Try Sample App

To meet your expectations, we suggest you try out our sample app. The sample app is built with full functionalities so that you can figure out the flow and main activities of common chat apps.  We provide you with two options to start with the sample app: 
1. Try Sample App only or
2. Try Sample App with Sample Dashboard

### Try Sample App Only

To run all of the sample code, you need to install Git and NodeJS. Git will
be used to clone the repository so you can play around with the code locally.
NodeJS is needed to install and resolve dependencies to run the Sample App.
You can refer to their respected page for more detail installing them both.

You can download the sample app directly from our [github](https://github.com/qiscus/qiscus-sdk-web-sample),
or if you already installed Git you can just clone directly from your command
line.
```bash
$ git clone https://github.com/qiscus/qiscus-sdk-web-sample.git
```

After cloning finished, you will need to create simple server to run the sample
app. In the example below, we use `http-server` from nodejs package manager
to server Sample App locally.
```bash
# Install http-server from npm globally
$ npm install http-server -g
# Choose folder and run Web SDK Sample
$ cd qiscus-sdk-web-sample
$ http-server
```
If you want your sample app running with your own APP ID, you can change it in file vars.js which is located at assets/js/vars.js.

### Try Sample App With sample dashboard

If you have your own chat app, you may be wondering how you can manage your users. In this case, we provide a sample dashboard for user management. This sample dashboard can help you to figure out how to work with Qiscus Server Api for more advanced functionalities. You can go to https://www.qiscus.com/documentation/rest/list-api to know more about Server API.

> Note: We assume that you already downloaded the sample app. The sample app
> will be needed to work together with the sample dashboard.

You can explore the sample dashboard http://dashboard-sample.herokuapp.com/login to try it online, or you also can download the source code to deploy it locally or to your own server.

To start trying the sample dashboard on your end, you should carry out the following steps:
Clone sample dashboard in our [github](https://github.com/qiscus/dashboard-sample), or just copy the following code.
```bash
git clone https://github.com/qiscus/dashboard-sample.git
cd dashboard-sample
```

Before running the sample app on your local, first, you need to install composer.
```bash
composer install
php -S localhost:8000
```
> The sample dashboard provided Client API to enable your sample app get list of users. This API is based on PHP and used Composer as its dependency manager. Thus, you need to have PHP and Composer installed to use the API.

Now you would have successfully run the sample dashboard. However, do note that the sample app is running using our App ID. If you want the sample dashboard to be connected to your app with your own App ID, you need to change it inside *.env file*. You can find your own App ID and Secret Key in your own [Qiscus SDK dashboard](https://www.qiscus.com/dashboard).

If you are wondering how our sample app with dashboard worked, here some
ilustration:
![How Sample Work Illustration](https://cdn.rawgit.com/qiscus/qiscus-sdk-web/feature/docs/docs/images/1511248325-How+sample+work.png "How Sample Work Illustration")

There are 2 Server API that are used inside Qiscus Sample Dashboard:

1. ```.qiscus.com/api/v2.1/rest/get_user_list``` to get list of users from Qiscus SDK database, and
2. ```.qiscus.com/api/v2/rest/login_or_register``` to enable user login or register via Sample Dashboard.

The Sample Dashboard called these APIs inside main.js file. To use these APIs, you need to pass your APP ID and  set method and request parameter. 

To set method and request parameter, you can refer to [Get User List](https://www.qiscus.com/documentation/rest/list-api#get-user-list) and [Login and Register](https://www.qiscus.com/documentation/rest/list-api#login-or-register) in Server API Documentation.

```
//your-domain.com/api/contacts
Example: //dashboard-sample.herokuapp.com/api/contacts
```
You will get the response as follow:
```JSON
{
   "results":{
      "meta":{
         "total_data":123,
         "total_page":6
      },
      "users":[
         {
            "avatar_url":"https:\/\/d1edrlpyc25xu0.cloudfront.net\/kiwari-prod\/image\/upload\/75r6s_jOHa\/1507541871-avatar-mine.png",
            "created_at":"2017-12-05T08:07:58.405896Z",
            "email":"sample@email.com",
            "id":452773,
            "name":"sample",
            "updated_at":"2017-12-05T08:07:58.405896Z",
            "username":"sample"
         }
      ]
   },
   "status":200
}
```
