# 구글 챗봇 Custom Payload, Web Demo, Dialogflow Messenger

Intents 이름: 구글챗봇의 Custom Payload를 이용해 리치 설명, 정보, 그림, 버튼, 선택, 리스트 등을 처리하는 프로그램을 설명한다.

다음 사이트를 참조해서 만들었습니다.
참조사이트 : https://miningbusinessdata.com/dialogflow-messenger-tutorial/


## 1. Description type :  
Intents 이름: richDes   
Training phrases : 리치설명

<img src="https://user-images.githubusercontent.com/37902752/132096660-0e6092a2-3528-4383-8387-741b84e46284.png" width="400" height="400" />
Custom Payload

```
{
  "richContent": [
    [
      {
        "title": "전등 리스트",
        "type": "description",
        "text": [
          "안방전등",
          "거실전등"
        ]
      }
    ]
  ]
}
```

## 2. Info type
Intents 이름:  richInfo  
Training phrases : 리치정보

<img src="https://user-images.githubusercontent.com/37902752/132097458-c18f3640-d504-4945-8845-2a0c2d630f75.png" width="400" height="400" />
부제목을 누르면 홈페이지로 링크합니다.
<br>Custom Payload

```
{
  "richContent": [
    [
      {
        "type": "info",
        "title": "제목",
        "subtitle": "부제목",
        "image": {
          "src": {
            "rawUrl": "http://i2r.link/image/i2r_small.png"
          }
        },
        "actionLink":"https://i2r.link"
      }
    ]
  ]
}
```

## 3. Image type
Intents 이름:  richImage 
Training phrases : 리치그림

<img src="https://user-images.githubusercontent.com/37902752/132097787-801ef826-d18a-445d-9081-ef982ada9446.png" width="400" height="400" />
Custom Payload 

```
{
  "richContent": [
    [
      {
        "type": "image",
        "accessibilityText":"MBD Image",
        "rawUrl": "http://i2r.link/image/sunset.jpg"
      }
    ]
  ]
}
```

## 4. Button type
Intents 이름:  richButton 
Training phrases : 리치버튼

<img src="https://user-images.githubusercontent.com/37902752/132097950-6c5542ee-b6f3-48e7-a480-4d95044827a4.png" width="400" height="400" />
Custom Payload 

```
{
  "richContent": [
    [
      {
        "link":"http://i2r.link",
        "text": "Go to Idea to Real",
        "icon": {
          "type":"link",
          "color":"#FF9800"
        },
        "type": "button"
      }
    ]
  ]
}
```

## 5. Suggestion Chips
Intents 이름:  richSuggestion  
Training phrases : 리치선택

<img src="https://user-images.githubusercontent.com/37902752/132098161-5bbdddfa-c40d-4650-ab83-3f7fdd8a9c47.png" width="400" height="400" />
Custom Payload 

```
{
  "richContent": [
    [
      {
        "type":"chips",
        "options": [
          {
            "text":"yes"
          },
          {
            "text":"no"
          }
        ]
      }
    ]
  ]
}
```

## 6. List Response Type
Intents 이름:  richList 
Training phrases : 리치리스트

<img src="https://user-images.githubusercontent.com/37902752/132098282-bed5abf4-96a8-4ee0-904a-8f842a93896f.png" width="400" height="400" />
Custom Payload 

```
{
  "richContent": [
    [
      {
        "title":"List item 1 title",
        "subtitle":"List Item 1 subtitle",
        "type":"list",
        "event": {
          "parameters":{},
          "name":"WELCOME",
          "languageCode":"en"
        }
      },
      {
        "type":"divider"
      },
      {
        "title":"List item 2 title",
        "subtitle":"List Item 2 subtitle",
        "type":"list",
        "event": {
          "parameters":{},
          "name":"PARALLEL",
          "languageCode":"en"
        }
      }
    ]
  ]
}
```

아마존크라우드 서버에 아파치를 설치하고 "/var/www/html" 디렉토리에 "rich.html" 프로그램을 만든다.
rich.html 프로그램 

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script src="https://www.gstatic.com/dialogflow-console/fast/messenger/bootstrap.js?v=1"></script>
    <df-messenger
      intent="WELCOME"
      chat-title="NewAgent"
      agent-id="ae3dfeee-a9af-4929-a084-8e003a25b56e"
      language-code="ko"
    ></df-messenger>
  </head>
<body>
테스트 입니다.
</body>
</html>
```

그림 파일은 "/var/www/html/image"에 복사한다.

<img src="https://user-images.githubusercontent.com/37902752/132098924-bc3bc18e-17ce-4ae2-8037-3b923a22d9c2.png" width="400" height="400" />

김동일교수 유튜브목차 : http://i2r.link


