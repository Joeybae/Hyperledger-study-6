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
  
    a. npm install express --save
    
    b. express command 에러 시 npm install -g express-generator
    
    c. express --view=ejs myapp
    
    d. cd myadd
    
    e. npm install
    
    f. localhost:3000 으로 접속
   
  3) app.js 수정
  
    a. var get_page = require('./routes/get_page'); //추가
    
    b. var post_page = require('./routes/post_page'); //추가
    
    c. app.use('/get_page',get_page); //추가
    
    d. app.use('/post_page',post_page); //추가
    
  4) 라우터 만들기
    
   a. views/get_page.ejs
    
        var express = require('express'); 
        var router = express.Router();

        router.get('/', function(req, res, next) {
            res.render('get_page', { title: 'Express' });
        });

        module.exports = router;
      
   b. views/post_page.ejs
    
        var express = require('express'); 
        var router = express.Router();

        router.get('/', function(req, res, next) {
            res.render('post_page', { title: 'Express' });
        });

        module.exports = router;
