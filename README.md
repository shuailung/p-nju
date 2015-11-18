# p-nju

A python script to login NJU brass. You can use it to login NJU brass in a console instread of browser, which is useful when you are playing fun with a black window other than a colorful one. 

### How to use it
Replace values of varibles username and password(in line 67 and 68) with yours.
>        Example   
>            Orignal: 
>                username = 'XXXXXX'
>                password = 'XXXXXX'
>            Suppose your name and password are 'zhangsan' and '123456', replace the
>            olders with yours
>                username = 'zhangsan'
>                password = '123456'
### TO-DO
1. handler exceptions(IMPORTANT) 
2. a user-friendly interactive UI
3. cookie if needed
4. logout if you want
         
### How does it work?
1.  send request to http://p.nju.edu.cn. 
After receive response use re to extract 201510210840 which is used in request header.
response data format
```javascript
<script type="text/javascript">
   location.href="/portal/index.html?v=201510210840";
</script>
```
 
2.  send request to the real login page http://p.nju.edu.cn/portal_io/login .
    headers:
```javascript
POST /portal_io/login HTTP/1.1
Host: p.nju.edu.cn
Connection: keep-alive
Content-Length: 34
Accept: application/json, text/javascript, */*; q=0.01
Origin: http://p.nju.edu.cn
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/45.0.2454.99 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
DNT: 1
Referer: http://p.nju.edu.cn/portal/index.html?v=201510210840
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,en;q=0.6,zh-TW;q=0.4
```
        
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
