# api设计v1
## 统一返回格式
```json
{
    "code": 0,
    "message": "",
    "data": {}
}
```
 
## 书籍模块
### 发布书籍 POST /postBook
Request
```json
{
    "commodityType": "SELL",
    "bookName": "go语言编程",
    "originalPrice": 35,
    "sellPrice": 20,
    "catergory": "计算机",
    "outerLinkList": [
        {
            "title": "go语言编程【京东】",
            "url": "https://item.jd.com/12437839.html"
        },
        {
            "title": "go语言编程【豆瓣】",
            "url": "https://book.douban.com/subject/11577300"
        }
    ],
    "pictureUrlList": [
        "https://flowbook-pic.oss-cn-hangzhou.aliyuncs.com/1552735405007018.jpeg",
        "https://flowbook-pic.oss-cn-hangzhou.aliyuncs.com/1552735257723507.png"
    ]
}
```
Response
```json
{
    "id": 5
}
```

### 获得书籍列表 GET /listBook
Request
```json
{
	"pageNum":1,
	"pageSize":5,
	"orderBy":"book_name",
	"ascent":true
}
```
Response
```json
{
    "total": 5,
    "list": [
        {
            "id": 1,
            "userId": 1,
            "userName": "max",
            "commodityType": "SELL",
            "bookName": "max' book",
            "originalPrice": 35,
            "sellPrice": 20,
            "category": "未分类",
            "description": "",
            "isbn": "",
            "createTime": "2019-03-15T12:48:27.000+0000",
            "updateTime": "2019-03-15T12:48:27.000+0000",
            "pictureUrlList": [],
            "outerLinkList": []
        }
    ],
    "pageNum": 1,
    "pageSize": 5,
    "size": 5,
    "startRow": 1,
    "endRow": 5,
    "pages": 1,
    "prePage": 0,
    "nextPage": 0,
    "isFirstPage": true,
    "isLastPage": true,
    "hasPreviousPage": false,
    "hasNextPage": false,
    "navigatePages": 8,
    "navigatepageNums": [
        1
    ],
    "navigateFirstPage": 1,
    "navigateLastPage": 1
}
```

### 查询书籍详情 POST getBookInfo
Request
```json
{
	"id":2
}
```
Response
```json
{
    "id": 1,
    "userId": 1,
    "userName": "max",
    "commodityType": "SELL",
    "bookName": "max' book",
    "originalPrice": 35,
    "sellPrice": 20,
    "category": "未分类",
    "description": "",
    "isbn": "",
    "createTime": "2019-03-15T12:48:27.000+0000",
    "updateTime": "2019-03-15T12:48:27.000+0000",
    "pictureUrlList": [],
    "outerLinkList": []
}
```

## 订单模块
### 创建订单 POST /createOrder
Request
```json
{
	"bookId": 1,
	"dealingMethod":"ONLINE",
	"comment":"nothing"
}
```
Response
```json
{
	"id":12 //订单id
}
```

### 确认订单 POST /confirmOrder
Request
```json
{
	"id":12
}
```
Response
```json
{
	"success":true,
	"message":"nothing"
}
```

### 完成交易 POST /completeOrder
Request
```json
{
	"id":12
}
```
Response
```json
{
	"success":true,
	"message":"nothing"
}
```

### 取消交易 POST /cancelOrder
Request
```json
{
	"id":12
}
```
Response
```json
{
	"success":true,
	"message":"nothing"
}
```

#flowbook/api