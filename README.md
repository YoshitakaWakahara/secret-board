# secret-board(匿名掲示板)

# 1.User Story

1. 認証されたユーザーは、匿名で掲示板の閲覧・書き込みができる。

1. 認証されたユーザーは、自身の投稿のみ削除ができる。

1. 管理者は、誰が投降したかを知ることができる。

1. 管理者は、すべての投稿を削除できる。

# 2.Functional requirements

1. ユーザーを認証すること

1. 認証したユーザーのみに投稿内容の閲覧を許可すること

1. 認証したユーザーのみに投稿を許可すること

1. 認証したユーザーのうち、自身の投稿内容のみの削除を許可すること

1. 匿名だが1日内であれば同じユーザーであることを識別させること

1. 下記の管理人機能があること

   1. 管理人の投稿だと識別させること

   1. 管理人にはすべての投稿の削除を許可すること

   1. 管理人にはどのアカウントの書き込みか判別させること

# 3.UI

https://xd.adobe.com/view/b30bcc8e-b150-4cdd-6007-decc8949295f-c53a/

# 4.URI

| Method | Path&Query | Process | Remarks |
----|---- | ---- | ---- |
| GET | /posts | Show all posts |
| POST | /posts | Post and Redirect | Redirect: use statuscode = 300 |
| POST | /posts?delete=1 | Delete | Since <form> tag can only use get.posts |
| GET | /logout | Logout | Release basic authentication |
| GET | /favicon.ico | Favicon |  |

# 5.Module

| FilePath | Role |
---- | ---- |
| index.js | Start http server |
| lib/router.js | Route request to handler |
| lib/posts-handler.js | Response to /posts request |
| lib/handler-utils.js | Response to other requests |
| lib/post.js | Get, Add, Delete posts |

# 6.Dependencies
