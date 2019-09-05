# Hyperledger-study-6

하이퍼레져 앱 만들기 실습 6일차 - express ejs api 예제 공부

목표

  1) form 에 텍스트를 받는 input
  
  2) form 을 전송하는 submit 버튼
  
  3) submit 으로 전송된 데이터를 표현하는 페이지

세 가지 사항을 GET 과 POST 로 구현한다.

실습

  1) package.json 만들기 - npm init
  
  2) express 설치
  
    npm install express --save
    
    express command 에러 시 npm install -g express-generator
    
    express --view=ejs myapp
    
    cd myadd
    
    npm install
    
    localhost:3000 으로 접속
   
  3) app.js 수정
  
    var get_page = require('./routes/get_page'); //추가
    
    var post_page = require('./routes/post_page'); //추가
    
    app.use('/get_page',get_page); //추가
    
    app.use('/post_page',post_page); //추가
    
  4) 라우터 만들기
    
   a. routes/get_page.js
    
        var express = require('express'); 
        var router = express.Router();

        router.get('/', function(req, res, next) {
            res.render('get_page', { title: 'Express' });
        });

        module.exports = router;
      
   b. routes/post_page.js
    
        var express = require('express'); 
        var router = express.Router();

        router.get('/', function(req, res, next) {
            res.render('post_page', { title: 'Express' });
        });

        module.exports = router;
        
  5) 뷰 만들기
    
   a. views/get_page.ejs
   
    <!DOCTYPE html> 
    <html>
        <head>
            <title><%= title %></title>
            <link rel='stylesheet' href='/stylesheets/style.css' />
        </head>
        <body>
            <div>GET test</div>
            <form action="/result_page" method="get">
                <input type="text" name="id" placeholder="Enter id here">
                <input type="text" name="age" placeholder="Enter age here">
                <input type="submit" value="Submit">
            </form>
        </body>
    </html>
    
   b. views/post_page.ejs
   
     <!DOCTYPE html> 
      <html>
          <head>
              <title><%= title %></title>
              <link rel='stylesheet' href='/stylesheets/style.css' />
          </head>
          <body>
              <div>POST test</div>
              <form action="/result_page" method="post">
                  <input type="text" name="id" placeholder="Enter id here">
                  <input type="text" name="age" placeholder="Enter age here">
                  <input type="submit" value="Submit">
              </form>
          </body>
      </html>

