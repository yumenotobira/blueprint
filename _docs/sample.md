# Group Questions

質問に関するリソース

## Question Collection [/api/v1/questions]

### List All Questions [GET]

+ Response 200 (application/json)

    [
      {
        "question": "Favorite programming language?",
        "published_at": "2014-11-11T08:40:51.620Z",
        "url": "questions/1",
        "choices": [
            {
              "choice": "Swift",
              "url": "/questions/1/choices/1",
              "votes": 2048
            }, {
              "choice": "Python",
              "url": "/questions/1/choices/2",
              "votes": 1024
            }
        ]
      }
    ]

### 新しい質問を作る [POST]

このアクションを使うことで新たな質問を作ることができます。

このアクションには質問と回答の選択肢の配列が必要です。

+ Parameters
  + question (string) - 質問
  + choices (array[string]) - 選択肢の配列

+ Request (application/json)

    {
      "question": "Favorite programming language?",
      "choices": [
        "Swift",
        "Python",
        "Objective-C",
        "Ruby"
      ]
    }

+ Response 201 (application/json)

  + Headers

    Location: /question/1

  + Body
      {
        "question": "Favorite programming language?",
        "published_at": "2014-11-11T08:40:51.620Z",
        "url": "questions/1",
        "choices": [
            {
              "choice": "Swift",
              "url": "/questions/1/choices/1",
              "votes": 0
            }, {
              "choice": "Python",
              "url": "/questions/1/choices/2",
              "votes": 0
            }, {
               "choice": "Objective-C",
               "url": "/questions/1/choices/3",
               "votes": 0
            }, {
               "choices": "Ruby",
               "url": "/questions/1/choices/4",
               "votes": 0
            }
        ]
      }

## Question [/api/v1/questions/{?question_id}]

+ Parameters
  + question_id: "1" (number) - 質問のIDを整数で指定

### 質問の詳細を見る [GET]

+ Response 200 (application/json)

      {
        "question": "Favorite programming language?",
        "published_at": "2014-11-11T08:40:51.620Z",
        "url": "questions/1",
        "choices": [
            {
              "choice": "Swift",
              "url": "/questions/1/choices/1",
              "votes": 2048
            }, {
              "choice": "Python",
              "url": "/questions/1/choices/2",
              "votes": 1024
            }
        ]
      }

### 質問を削除する [DELETE]

+ Response 200 (application/json)

+ Response 404
