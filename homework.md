- HTTPのHeaderについて  
  headerは、クライアントからのリクエストや、サーバーからのレスポンズ時に追加で情報を渡すことができる。

- おもしろそうなHeaderを1つあげる
  - エンティティヘッダー（Entity Header）について説明する。  
  エンティティヘッダーとは、メッセージボディの情報を保有するHTTP Headerである。  
  エンティティヘッダーの要素として「Content-Length」や「Content-Length」などがあり、メッセージボディに関する情報が含まれていることがわかる。  
  エンティティヘッダーは、リクエストヘッダーやレスポンズヘッダーに含まれていることが多いが、それぞれのヘッダーとは独立して存在している。  
  - 【参考】[MDN web dogs - Entity header(エンティティヘッダー)](https://developer.mozilla.org/ja/docs/Glossary/entity_header)
  
  * * *
  
- Cookieについての説明
  - webから利用ユーザーのブラウザに送信されるログイン情報等を一時的に保存する仕組みのこと。  
  Cookieに保存された情報から、webサービス上でのユーザーのログイン状態の維持など、便利な機能が実現できる。
  
  * * *
  
- CookieとSessionIDの違い
  - Cookieは利用ユーザーのブラウザに情報が保存される仕組みである。  
  SessionIDはサーバー側に格納されている情報を受け取るための識別子であり、情報を保存する仕組みではない。
  - 【参考】[セッションとクッキーの違い - - SpringBoot - はてなブログ](http://ohs30359.hatenablog.com/entry/2015/09/04/235027)
  
  * * *
  
- Cookieの管理方法
  - サーバー側からのレスポンズとして「Set-Cookie」ヘッダーを送信することで、Cookieをユーザーのブラウザにセットすることができる。  
  Cookieに保存された情報は、ユーザからのリクエストの際に「Cookie」ヘッダーとしてサーバー側に送信されることで、
  サーバー側はユーザーの情報を習得することができる。  
  Cookieの保存期間や送信先URLの指定などの細かい設定も「Set-Cookie」ヘッダーやCookieのスコープを用いて行うことができる。
  - 【参考】[MDN web dogs - HTTP Cookie](https://developer.mozilla.org/ja/docs/Web/HTTP/Cookies)
  
  * * *
  
- SessionIDの管理方法
  - ユーザーとサーバーの通信状況をSessionとしてサーバー側に保存し、このSessionを習得するために必要となるSessionIDを
  「Set-Cookie」ヘッダーを用いてユーザーのブラウザに保存する。  
  Sessionを習得する際は、ユーザーからのリクエストの際に「Cookie」ヘッダーとして保存したSessionIDをサーバー側に送信することで、Sessionの参照を行うことができる。
  - 【参考】[6.4.1 セッション管理 - IPA](https://www.ipa.go.jp/security/awareness/administrator/secure-web/chap6/6_session-1.html)
  
  * * *
  
- Cookieを利用したSessionの管理方法以外のSessionの管理方法
  - HTMLの送信フォーム項目であるHiddenフィールドを用いる。  
  Hiddenフィールドとは、ブラウザからリクエストを送信するときに同時に送信される項目である。このフィールドにSessionIDを持たせることで、Sessionの管理を実現できる。  
  しかし、HiddenフィールドでのID管理はwwwブラウザを経由して行うため、改ざんや参照がされやすい。
  よって、サーバー側で指定されているセッション変数を用いるなどの工夫が必要になる。
  - 【参考】[1-5. hiddenは危険（セッション変数を利用しよう） - IPA](https://www.ipa.go.jp/security/awareness/vendor/programmingv1/a01_05.html)
  
  
  
  
