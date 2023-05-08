# Question API Detali

### 모든 질문 갯수 조회 [  *GET* ] 
질문의 모든 갯수를 반환해 줍니다.

### Request

```url
/question/total
```

### Response

[ *SUCCESS* ] HTTP Status **200**

```url
GET "total_question_count": (질문의 모든 갯수)
```

---

### 질문 미리보기 조회 [ *GET* ]
질문의 미리보기를 반환해 줍니다.

### Request
```url
GET /question/preview?question_idx={idx}
```

### Response 

[ *SUCCESS* ] HTTP Status **200**

```json
{
    "writer":         "idx에 해당하는 값",
    "title":          "idx에 해당하는 값",
    "view_count":     (idx에 해당하는 값),
    "answer_count":   (idx에 해당하는 값),
    "vote_count":     (idx에 해당하는 값)
}
```

[ *FAIL* ] HTTP Status **404**

```json
{
  "writer":         "No information was found corresponding to the passed query string",
  "title":          "No information was found corresponding to the passed query string",
  "view_count":     0,
  "answer_count":   0,
  "vote_count":     0
}
```

---

### 질문 조회 [ *GET* ]
질문의 상세한 정보를 반환해 줍니다.

### Request
```url
GET  /question/detail?question_idx={idx}
```

### Response

[ *SUCCESS* ] HTTP Status **200**

```json
{
  "index":        (idx에 해당하는 값),
  "writer":       "idx에 해당하는 값",
  "title":        "idx에 해당하는 값",
  "content":      "idx에 해당하는 값",
  "view_count":   (idx에 해당하는 값),
  "answer_count": (idx에 해당하는 값),
  "vote_count":   (idx에 해당하는 값)
}
```

[ *FAIL* ] HTTP Status **404**

```json
{
  "index":        0,
  "writer":       "No information was found corresponding to the passed query string",
  "title":        "No information was found corresponding to the passed query string.",
  "content":      "No information was found corresponding to the passed query string.",
  "view_count":   0,
  "answer_count": 0,
  "vote_count":   0
}
```

---

### 질문 하기 [  *POST*  ]
질문을 등록합니다. 

### Request 
```url
POST  /question/ask
```
```json
{
  "writer":       "사용자이름",
  "title":        "질문 제목",
  "content":      "질문 내용",
}
```

### Response
[ *SUCCESS* ] HTTP Status **200**
```json
{
  "status": 200,
  "message": "success question ask"
}
```

[ *FAIL* ] HTTP Status **422**
```json
{
  "status": 422,
  "message": "parsing error"
}
```

