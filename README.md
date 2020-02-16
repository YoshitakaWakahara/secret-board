# secret-board

#0.Functional requirements

#1.UI

https://xd.adobe.com/view/b30bcc8e-b150-4cdd-6007-decc8949295f-c53a/

#2.URI

| Method | Path&Query | Process | Remarks |
----|---- | ---- | ---- |
| GET | /posts | Show all posts |
| POST | /posts | Post and Redirect | Redirect: use statuscode = 300 |
| POST | /posts?delete=1 | Delete | Since <form> tag can only use get.posts |
| GET | /logout | Logout | Release basic authentication |
| GET | /favicon.ico | Favicon |  |

#3.Module

| FilePath | Role |
---- | ---- |
| index.js | Start http server |
| lib/router.js | Route request to handler |
| lib/posts-handler.js | Response to /posts request |
| lib/handler-utils.js | Response to other requests |
| lib/post.js | Get, Add, Delete posts |
