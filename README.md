# apidoc 매뉴얼

$ express projectName

$ npm i apidoc -g

root에 apidoc.json 추가
```
{
	"name": "example-inherit",
    "version": "0.1.0",
    "description": "apiDoc inherit example",
	"url": "localhost:3000",
	"order": [
		"adproduct",
		"brand",
		"category",
		"group",
		"index",
		"info",
		"inven",
		"job",
		"point",
		"product",
		"tags",
		"tc"
	]
}
```

app.js 에 아래 내용 추가, 개발 모드에서만 보기 위해
```
if (app.get('env') === 'development') {
    app.use('/doc', express.static('apidoc'));
});
```

각 api 위에 추가 별도 사용 방법은 http://apidocjs.com/
```
/**
 * @api {get} /inven/list/:program_id& 상품 조회 API
 * @apiName getInventoryList
 * @apiGroup inven
 * @apiVersion 0.0.0
 * @apiDescription 포인트 등록 화면에서 오른쪽 상품탭에 표시할 아이템을 조회하는 API이다.
 * 
 * @apiParam {String} program_id 프로그램의 유니크 아이디
 * 
 * @apiParamExample {json} Request-Example: 
 *  {
 *      "program_id": "S01_V0000330171",
 *  }
 * 
 * @apiSuccessExample {json} Success-Respoonse:
 *  HTTP/1.1 200 OK
 *  {
 *      {
 *          "code": 200,
 *      }
 *  }
 */
 ```

apidoc 추출 명령어 터미널에서 실행
```
$ apidoc -i routes/ -o apidoc/
```

npm start 후 /doc 확인