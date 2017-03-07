##js获取url里的参数

```javascript
function GetRequest() { 
        //例如 http://localhost/demo/demo.html?aaa=onestopweb&bbb=demo&ccc=chaoyi 
        //location.search 获取问号及后面的参数 ?aaa=onestopweb&bbb=demo&ccc=chaoyi 
        var url = location.search; 
        var theRequest = new Object; 
        if (url.indexOf("?") != -1) { 
            var str = url.substr(1); 
            strs = str.split("&"); 
            for(var i = 0; i < strs.length; i ++) { 
                theRequest[strs[i].split("=")[0]]=unescape(strs[i].split("=")[1]); 
            } 
        } 
        return theRequest; 
    } 
    var ClientRequest = GetRequest(); 
    console.info(ClientRequest); 
    var ReauesKey = ClientRequest['aaa']; 
    console.log(ReauesKey);   // onestopweb
```