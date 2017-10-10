# Nginx Config

```bash
location /abc/ {
  proxy_pass http://127.0.0.1:2000/;
  proxy_set_header   Host $host;
}
```

와 같은 형식일 경우에는 http://localhost/abc/def/gh.html 이 proxy를 통해서 

`/def/gh.html`

로 들어가고

```bash
location /abc/ {
  proxy_pass http://127.0.0.1:2000;
  proxy_set_header   Host $host;
}
```
와 같은 형식일 경우에는 http://localhost/abc/def/gh.html 이 proxy를 통해서 

`/abc/def/gh.html`

로 들어감.
차이점은 proxy_pass 의 url맨뒤에 `/`가 있는가 없는가로 구분됨.
