# Two-Tier-Enterprise-App-and-API-Development-with-Angular-and-Sails

## 01. Introduction


### 04. Sails Setup

    mkdir socialfleet
    cd socialfleet

    npm install -g sails
    sails new --no-frontend
    sails lift


### 05. Web API Demo

    sails generate api user
    sails lift
    2

    http://localhost:1337/user
    http://localhost:1337/user/create?name=Alex
    http://localhost:1337/user/create?name=Tim
    http://localhost:1337/user/create?name=Tim&email=a@a.a
    http://localhost:1337/user

___

## 02. Posting and Authentication


### 03. Creating Our Login Service Endpoint Skeleton

    http://localhost:1337/user/login
    В консоли сервера появился вывод сообщения.

    В models.js разкомментировали migrate: 'alter', чтобы sails не задавал вопросов при старте


### 04. Registering Our App with Twitter

    https://apps.twitter.com/

    Name: socialfleet
    Description: a social media scheduler
    Website: http://marley.org
    Callback URL: http://127.0.0.1:80


### 05. Setting up Angular

    mkdir backend
    mv * ./backend

    mkdir frontend
    cd frontend
    npm init

    npm install --save-dev bower
    bower init
    bower install --save angular


### 06. Automating Tasks with Gulp

    cd frontend/
    npm install --save-dev gulp
    gulp


### 07. Setting up the Server

    cd frontend/
    npm install --save gulp-webserver
    gulp

localhost:8000


### 08. Optimizing Our Gulp Tasks

    gulp

### 09. How to Autoload Vendor Files with Gulp

    cd frontend/
    npm install --save-dev main-bower-files
    npm install --save-dev gulp-inject
    gulp


### 10. Autoloading Our Custom Scripts

    gulp


### 11. Creating the Login Controller

    gulp
    http://localhost/

По клику по кнопке в консоли печатается "works"


### 12. Using Gulp Watchers to Autorun Scripts

    cd frontend/
    npm install --save-dev del
    gulp

___

## 03. Posts


### 02. Twitter Login Setup with Satellizer

https://github.com/sahat/satellizer

    cd frontend/
    bower install --save satellizer
    gulp


### 03. How to Talk to Our Backend with a Proxy

    cd backend/
    sails lift


    cd frontend/
    gulp

    http://localhost/

    По нажатию на кнопку получаем сообщение "hello"


### 04. Finishing Authentication

https://github.com/sahat/satellizer/blob/master/examples/server/node/server.js


    cd backend/
    npm install --save request
    npm install --save jwt-simple
    npm install --save moment

    apps.twitter.com
    v Allow this application to be used to Sign in with Twitter

В chrome при попытке авторизации получаем в Resources -> Local Storage -> satellizer_token



### 05. Tweeting from Our Backend

    cd backend/
    sails generate controller post

https://github.com/ttezel/twit/

    npm install --save twit

apps.twitter.com -> Permissions  
Read, Write and Access direct messages  

В chrome удаляем Resources -> Local Storage -> satellizer_token  
Удаляем файл backend/.tmp/localDiskDb.db

Делаем в браузере login.

Из файла backend/.tmp/localDiskDb.db вставляем twittetToken и twittetTokenSecret в PostControllet.js

По нажатию на tweet, в твиттере появилась запись "hello world!!!".


### 06. Securing Our Tweets with Policies

В паблике персональные данные по адресу:

http://localhost:1337/user

После внесения правок

http://localhost/

tweet получили сообщение в консоли:

    message: 'Status is a duplicate.',
    statusCode: 403,
    twitterReply: '{"errors":[{"code":187,"message":"Status is a duplicate."}]}',
    code: 187,
    allErrors: [ { code: 187, message: 'Status is a duplicate.' } ] }


### 07. Tweeting with Authenticated User

___


## 04. Making a New Post


### 02. Styling with Bootstrap

bootswatch.com -> Sandstone


### 03. Setting up Our Nav

(Добавили кнопки login, logout)


### 04. Passing the Tweet Message from the Frontend


### 05. Setting Our Posting Date with the Datepicker


    cd frontend/
    bower install --save angular-bootstrap
    Answer:: [3]


### 06. Using Timepicker and Improving Our Layout


### 07. Getting Our Datetime Ready for the Backend

### 08. Saving Our Post on the Backend

    cd backend/
    sails generate model post


В консоли backend печатаем дату и времся из формы frontend

### 09. Associating Posts with Users

+ печатаем owner

### 10. Getting All Our Posts


### 11. Displaying All Our Posts

___

## 05. Edit Posts

### 02. Routing with UI-Router

    cd frontend/
    bower install --save angular-ui-router


### 03. Creating a New Post State

### 04. Getting Our Post Details

http://localhost/#/post?id=3

В response http://localhost/api/post/3 данные с sails.


### 05. Securing Our Own Posts with Policies

### 06. Displaying Our Existing Posts

### 07. Editing Our Posts

http://localhost/#/post?id=3


### 08. Making Our Post List Clickable

### 09. Getting Some Feedback with Toastr Notifications

    cd frontend/
    bower install --save angular-toastr
    bower install --save angular-animate

toastr.css пришлось отдельно скопировать в app/


### 10. Deleting a Post

___

## 06. Scheduling Service

### 02. Setting up Our Service with a Timed Interval

    cd backend
    node sheduler.js


### 03. Getting Posts That Are Ready to Send

В chrome удаляем Resources -> Local Storage -> satellizer_token  
Удаляем файл backend/.tmp/localDiskDb.db

Делаем в браузере login.

    cd backend
    node sheduler.js

С первого раза не создалась запись twitterToken в новом backend/.tmp/localDiskDb.db


### 04. Populating User Data for the Tweet

    cd backend
    node sheduler.js

### 05. Posting Our Scheduled Posts to Twitter

    cd backend
    node sheduler.js


### 06. Marking Posts as Sent

    cd backend
    node sheduler.js

### 07. Our Final and Big Test

### 08. Improving Our Visual Design

### 09. A Better Looking Login

### 10. Fixes and Wrapping Up
