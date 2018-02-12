# go-for-web-dev

Go for Web Development was created by Packt Publishing. It was originally released on 12/29/15. [Commits](https://github.com/haruelrovix/go-for-web-dev/commits/master) on this branch following course on [Lynda](https://www.lynda.com/Go-tutorials/Go-Web-Development/516402-2.html).

My path:
- Day 1: [On Track With Golang](https://www.codeschool.com/courses/on-track-with-golang) by [Code School](https://www.codeschool.com).
- Day 2: [Learning Go for Web Development](https://www.lynda.com/Go-tutorials/Go-Web-Development/516402-2.html) by [Lynda](https://www.lynda.com), _3 chapters out of 6_.

### Prerequisite
1. [Go](https://github.com/golang/go)<br>
`go version go1.9.4 darwin/amd64`
2. [SQLite](https://www.sqlite.org/)<br>
`SQLite version 3.16.0 2016-11-04 19:09:39`

### Setting Database
1. Start db, `sqlite3 dev.db`
2. Add schema below<br>
```sql
CREATE TABLE books(
  pk integer primary key autoincrement,
  title text,
  author text,
  id text,
  classification text
);
```
3. Check, `.schema`

### How to Run
1. Clone this repository<br>
`git clone https://github.com/haruelrovix/go-for-web-dev.git`
2. Run<br>
`go run main go`
3. Open browser at `:8080`
<img src="https://i.imgur.com/tA0SzA3.png" alt=":8080" width="50%" />

### Debugging
1. Install [Delve](https://github.com/derekparker/delve), a debugger for the Go programming language.
2. Configuraton for `launch.json` in VS Code.
```javascript
  "configurations": [
    {
      "name": "Launch",
      "type": "go",
      "request": "launch",
      "mode": "debug",
      "remotePath": "",
      "port": 2345,
      "host": "127.0.0.1",
      "program": "${workspaceFolder}",
      "env": {},
      "args": [],
      "showLog": true
    }
  ]
```
3. Debug - Start Debugging (F5)
<img src="https://i.imgur.com/7jiI5YT.png" alt="Debugging Go using VS Code" width="50%" />

4. For logging, it uses [negroni](https://github.com/urfave/negroni).

```java
[negroni] listening on :8080
[negroni] 2018-02-12T10:59:38+07:00 | 200 |      11.160448ms | localhost:8080 | GET /
[negroni] 2018-02-12T10:59:53+07:00 | 200 |      2.121296ms | localhost:8080 | DELETE /books/8
```

### References
- [Getting Started with SQLite on Mac OS X](http://razorsql.com/articles/sqlite_mac.html)
- [Exit a SQLite3 database](https://stackoverflow.com/questions/34747624/exit-a-sqlite3-database) 😂
- [Database drivers for SQLite in Go](https://astaxie.gitbooks.io/build-web-application-with-golang/en/05.3.html)
- [Debugging Go code using VS Code](https://github.com/Microsoft/vscode-go/wiki/Debugging-Go-code-using-VS-Code)
- [An experimental classification web service](http://classify.oclc.org/classify2/)
