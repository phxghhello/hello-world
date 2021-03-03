# 面试题
## CSS
\###1.一个盒子垂直水平居中有哪些方法？（2~3种方法）
space-bettewn属性
\###2.flex怎么使用，flex:1代表了什么（三个属性）
\###3.使用自适应布局的时候用rem,为什么可以实现自适应布局，在不同的手机端表现得是什么
rem是基于html的字体大小来进行布局的（问：不同的移动端是有不同的html字体大小吗，在拿到设计图是怎么计算的）除以16px(问：16px是基于什么来的)
\##4.http计算机基础相关
三次握手四次挥手
常见状态码
\##vue
axios的底层是怎么实现的，用什么实现的（配套AJAX问题）
\###5.vue的生命周期
mounted和created的区别：
created的时候，他的html的节点都没有渲染出来
mounted的时候，可以进行数据请求，进行数据绑定（此时HTML的结构已经出来了，可以将数据绑定到DOM结构上）
\###6.组件传值分为（父传子、子传父、兄弟组件之间传值）
\###7.keep-alive是怎么使用的
缓存、会多出来几个生命周期
\###8.VUE双向绑定的原理
数据劫持objectDefinePropoty
数据劫持之后，通过发布订阅模式
\##JS
\###9.跨域是有哪几种方式实现的（什么是跨域，限制了什么，不同源的话会进行什么策略）
跨域的方式有：jsonP、nigix的代理、websocket以及php端修改header。
代理设置了location的哪一项？
websocket是怎么进行跨域的？
php修改header为很么修改了就想能跨域了？
\###10.this指向
普通函数和箭头函数的this，以及怎么改变普通函数里的this指向
\###11.apply、call、bind,区别
apply怎样实现bind
\##ES6
\###12.promise和async await有什么区别
await有什么特点
这两个方法报错了怎么抓取
\###13.ES6的新特性有哪些
promise async await class继承、解构赋值
定义const、var、let、箭头函数
\###14.let、var、const的区别
const定义的对象是可以改变的（定义的是指向对象的地址）



css
\1. 一个盒子垂直水平居中有哪些方法

https://www.cnblogs.com/gzy-tw/p/11205854.html

\2. flex:1 是什么意思

https://www.runoob.com/cssref/css3-pr-flex.html

\3. rem为什么可以实现自适应布局

https://blog.csdn.net/qq_42707446/article/details/93200711

http
\1. 三次握手和四次挥手

https://www.pianshen.com/article/8384298792/

\2. 常见状态码

301和302的区别 https://blog.csdn.net/banana960531/article/details/85621865

\3. http的8种请求方式及区别

Vue
\1. axios底层是怎么实现的

https://blog.csdn.net/luchuanqi67/article/details/81329358 https://www.jianshu.com/p/8bc48f8fde75

\2. Vue的生命周期

created和mounted的区别

https://cn.vuejs.org/v2/guide/instance.html

\3. Vue之间父子组件传值

父传子、子传父、兄弟组件之间的传值 https://cn.vuejs.org/v2/guide/components-props.html https://www.jianshu.com/p/af9cb05bfbaf https://www.cnblogs.com/chen-yi-yi/p/11152391.html

\4. keep-alive的作用

https://www.jianshu.com/p/9523bb439950

\5. Vue的双向绑定原理

https://www.jianshu.com/p/78b31df97b70



# 试题整理

刷题错题整理：

1. `setTimeout`的回调函数会**在遍历结束后执行**；

2. static静态方法被设为只能被创建他们的构造器使用，并且不能传递给实例；

   即 **静态方法不能被实例调用**；

3. **函数名**可以**用点语法新增属性**因为函数也是对象（**除了基本类型，都是对象**）；

   **除了基本对象，所有对象都有原型**；

4. 不能够直接给构造函数添加属性，要通过原型结构给函数添加属性；

5. 在**测试相等性**时，基本类型通过它们的值进行比较；对象通过它们的引用进行比较（判断是否具有**对内存中相同位置的引用**）；

6. **关闭tab标签页后，`sessionStrorage`存储的数据才会删除**；

7. 使用var声明变量，可以使用**相同的名称，变量将保存最新值**；

8. 如果对象有两个相同名称的键，则键会被替换掉：它仍然处于第一个键出现的位置，但是值是最后出现的那个键的值；

9. **隐式字符串化**：当对象的键也被设置为对象时，会字符串化一个对象，它会变成`[Object object]`;

10. 只有6种falsy值：**undefined、null、NaN、0、‘’、false**（注：**对象是true**）；

11. `typeOf typeOf 1 =“string”`；

    `typeOf`检测null类型时，返回的是`object`；

    `typeOf`可以检测出的变量的基本数据类型：Number、String、Boolean、Undefined、Symbol、Object（null返回的是Object）、function

12. BOM对象：Screen、Location、History、Navigator；

13. 不要在块内声明一个函数，如果需要的话，就使用函数表达式；

14. **new构造函数的步骤**：（摘自红宝书P145）

    new ClassA(…)

    1. **创建**一个新对象；

       ```
       var obj = {};
       //或者
       var obj = new Object();
       ```

    2. 将构造函数的**作用域赋给新对象**（用新对象的隐式原型指向构造函数的显式原型，用call改变this指向，因此this就指向了这个新对象）；

       ```
       obj.__proto__ = ClassA.prototype;//设置原型链
       ClassA.call(obj);//更改this指向
       ```

    3. 执行构造函数中的代码（**为这个新函数添加属性**）；

    4. **返回**新对象；

15. `stopPropagation()`**阻止事件冒泡**，但不会阻止定义在元素上的其他事件；

    `stopImmediatePropagation()`**彻底阻止事件**，在其之后绑定在元素上的其他监听事件都不会触发；

16. 视口的缩放配置的目的：为了让css样式中的逻辑像素匹配手机终端的物理像素，让网页视图适合手机屏幕；

    使用rem单位的目的：为了让一份代码适应大部分不同屏幕的手机；

    自适应：在同一终端下，页面布局根据视口本身的变化而自动调节布局（如PC端页面变化、resize事件等）；

    响应式：指页面根据检测到的不同终端类型，自动调整布局；

17. 执行优先级由高到低：**小括号(xxx) > 属性访问. > new foo() > foo()**

```
function getName(){
    console.log(1)
}
function Foo() {
    this.getName = function () {
        console.log(2); 
    };
    return this;
}
Foo.getName = function () {
    console.log(3);
};
var a=new Foo.getName();//属性.的优先级高于new foo()，该行等于new (Foo.getName)();，返回3
var b=new Foo().getName();//new foo()的优先级高于foo()，该行等于(new Foo()).getName()；，返回2
var c=new new Foo().getName();//new foo()优先级低于属性.，该行等于new (new Foo().getName)();，相当于new一个new foo()的getName属性函数，返回2
//再举个栗子
new Date().getTime();//===((new Date()).getTime)()
(new Date).getTime();//===((new Date()).getTime)()
new Date.getTime();//Uncaught TypeError: Date(...).getTime is not a function；===new (Date.getTime)()
```

### 1. 跨域怎么实现？jsonp的原理是什么？

跨域，指的是浏览器不能执行其他网站的脚本。浏览器执行`javascript`脚本时，会检查这个脚本属于哪个页面，如果不是同源页面，就不会被执行。**跨域并不是请求发不出去，请求能发出去，服务端能收到请求并正常返回结果，只是结果被浏览器拦截了**。

**同源策略限制内容有：**

- Cookie、LocalStorage、IndexedDB 等存储性内容
- DOM 节点
- AJAX 请求发送后，结果被浏览器拦截了

![img](https://codingwithalice.github.io/img/assets_2019/1620)

解决办法：

①**JSONP**：注意JSONP只支持GET请求，不支持POST请求，**不安全可能会遭受XSS攻击**。

原理：ajax请求受同源策略影响，不允许进行跨域请求，而**script标签src属性**中的链接却可以**访问跨域的js脚本**，利用这个特性，服务端不再返回JSON格式的数据，而是**返回一段调用某个函数的js代码**，在src中进行了调用，这样实现了跨域。

```
// index.html
function jsonp({ url, params, callback }) {
  return new Promise((resolve, reject) => {
    let script = document.createElement('script')
    window[callback] = function(data) {
      resolve(data)
      document.body.removeChild(script)
    }
    params = { ...params, callback } // wd=b&callback=show
    let arrs = []
    for (let key in params) {
      arrs.push(`${key}=${params[key]}`)
    }
    //创建一个<script>标签，把那个跨域的API数据接口地址，赋值给script的src,还要在这个地址中向服务器传递该函数名（可以通过问号传参:?callback=show）
    script.src = `${url}?${arrs.join('&')}`
    document.body.appendChild(script)
  })
}

jsonp({
  url: 'http://localhost:3000/say',
  params: { wd: 'Iloveyou' },
  callback: 'show'
}).then(data => {
  console.log(data)
})
//上面这段代码相当于向http://localhost:3000/say?wd=Iloveyou&callback=show这个地址请求数据，然后后台返回show('我不爱你')，最后会运行show()这个函数，打印出'我不爱你'
```

②**CORS**

浏览器会自动进行 CORS 通信，实现 CORS 通信的关键是后端。只要后端实现了 CORS，就实现了跨域。

**服务端设置 Access-Control-Allow-Origin 就可以开启 CORS**。 该属性表示哪些域名可以访问资源，如果设置通配符则表示所有网站都可以访问资源。

在发送请求时，分为两种情况，简单请求和复杂请求。

**简单请求：**

只要同时满足以下两大条件，就属于简单请求

条件1：使用**GET、HEAD、POST方法之一**；

条件2：**Content-Type的值是text/plain、multipart/form-data、application/x-www-form-urlencoded三者之一**；

**复杂请求：**

除了简单请求，就是复杂请求。

复杂请求的CORS请求，**会在正式通信之前，增加一次HTTP查询请求**，称为”预检”请求，**该请求是 option 方法的，通过该请求来知道服务端是否允许跨域请求**。

比如使用PUT方法进行后台请求的时候，后端需进行如下配置

```
// 允许哪个方法访问我
res.setHeader('Access-Control-Allow-Methods', 'PUT')
// 预检的存活时间
res.setHeader('Access-Control-Max-Age', 6)
// OPTIONS请求不做任何处理
if (req.method === 'OPTIONS') {
  res.end() 
}
// 定义后台返回的内容
app.put('/getData', function(req, res) {
  console.log(req.headers)
  res.end('我不爱你')
})
```

**③postMessage**

postMessage是HTML5 XMLHttpRequest Level 2中的API，且是为数不多可以跨域操作的window属性之一，它可用于解决以下方面的问题：

- 页面和其打开的新窗口的数据传递
- 多窗口之间消息传递
- 页面与嵌套的iframe消息传递
- 上面三个场景的跨域数据传递

**postMessage()方法允许来自不同源的脚本采用异步方式进行有限的通信，可以实现跨文本档、多窗口、跨域消息传递**。

```
otherWindow.postMessage(message, targetOrigin, [transfer]);
```

参数解释：

message: 将要发送到其他 window的**数据**。

targetOrigin:通过窗口的origin属性来**指定哪些窗口能接收到消息事件**，其值可以是字符串”*“（表示无限制）或者一个URI。在发送消息的时候，如果目标窗口的协议、主机地址或端口这三者的任意一项不匹配targetOrigin提供的值，那么消息就不会被发送；只有三者完全匹配，消息才会被发送。

transfer(可选)：是一串和message 同时传递的 Transferable 对象. 这些对象的所有权将被转移给消息的接收方，而发送一方将不再保有所有权。

**④websocket协议**

Websocket是HTML5的一个持久化的协议，它实现了浏览器与服务器的全双工通信，同时也是跨域的一种解决方案。**WebSocket和HTTP都是应用层协议，都基于 TCP 协议**。但是 **WebSocket 是一种双向通信协议，在建立连接之后，WebSocket 的 server 与 client 都能主动向对方发送或接收数据**。同时，WebSocket 在建立连接时需要借助 HTTP 协议，连接建立好了之后 client 与 server 之间的双向通信就与 HTTP 无关了。

原生WebSocket API使用起来不太方便，我们使用`Socket.io`，它很好地封装了webSocket接口，提供了更简单、灵活的接口，也对不支持webSocket的浏览器提供了向下兼容。

```
//本地文件socket.html向localhost:3000发生数据和接受数据

// socket.html
<script>
    let socket = new WebSocket('ws://localhost:3000');
    socket.onopen = function () {
      socket.send('我爱你');//向服务器发送数据
    }
    socket.onmessage = function (e) {
      console.log(e.data);//接收服务器返回的数据
    }
</script>

// server.js
let express = require('express');
let app = express();
let WebSocket = require('ws');//记得安装ws
let wss = new WebSocket.Server({port:3000});
wss.on('connection',function(ws) {
  ws.on('message', function (data) {
    console.log(data);
    ws.send('我不爱你')
  });
})
```

**⑤Node中间件代理（两次跨域）**

实现原理：**同源策略是浏览器需要遵循的标准，而如果是服务器向服务器请求就无需遵循同源策略。** 代理服务器，需要做以下几个步骤：

- 接受客户端请求 。
- 将请求 转发给服务器。
- 拿到服务器 响应 数据。
- 将 响应 转发给客户端。

![img](https://codingwithalice.github.io/img/assets_2019/1)

```
//本地文件index.html文件，通过代理服务器http://localhost:3000向目标服务器http://localhost:4000请求数据。

// index.html(http://127.0.0.1:5500)
 <script src="https://cdn.bootcss.com/jquery/3.3.1/jquery.min.js"></script>
    <script>
      $.ajax({
        url: 'http://localhost:3000',
        type: 'post',
        data: { name: 'xiamen', password: '123456' },
        contentType: 'application/json;charset=utf-8',
        success: function(result) {
          console.log(result) // {"title":"fontend","password":"123456"}
        },
        error: function(msg) {
          console.log(msg)
        }
      })
     </script>

// server1.js 代理服务器(http://localhost:3000)
const http = require('http')
// 第一步：接受客户端请求
const server = http.createServer((request, response) => {
  // 代理服务器，直接和浏览器直接交互，需要设置CORS 的首部字段
  response.writeHead(200, {
    'Access-Control-Allow-Origin': '*',
    'Access-Control-Allow-Methods': '*',
    'Access-Control-Allow-Headers': 'Content-Type'
  })
  // 第二步：将请求转发给服务器
  const proxyRequest = http
    .request(
      {
        host: '127.0.0.1',
        port: 4000,
        url: '/',
        method: request.method,
        headers: request.headers
      },
      serverResponse => {
        // 第三步：收到服务器的响应
        var body = ''
        serverResponse.on('data', chunk => {
          body += chunk
        })
        serverResponse.on('end', () => {
          console.log('The data is ' + body)
          // 第四步：将响应结果转发给浏览器
          response.end(body)
        })
      }
    )
    .end()
})
server.listen(3000, () => {
  console.log('The proxyServer is running at http://localhost:3000')
})

// server2.js(http://localhost:4000)
const http = require('http')
const data = { title: 'fontend', password: '123456' }
const server = http.createServer((request, response) => {
  if (request.url === '/') {
    response.end(JSON.stringify(data))
  }
})
server.listen(4000, () => {
  console.log('The server is running at http://localhost:4000')
})
```

**⑥nginx反向代理**

实现原理类似于Node中间件代理，需要你搭建一个**中转nginx服务器，用于转发请求**。

使用nginx反向代理实现跨域，**是最简单的跨域方式**。只需要修改nginx的配置即可解决跨域问题，支持所有浏览器，支持session，不需要修改任何代码，并且不会影响服务器性能。

实现思路：通过nginx配置一个代理服务器（域名与domain1相同，端口不同）做跳板机，反向代理访问domain2接口，并且可以顺便修改cookie中domain信息，方便当前域cookie写入，实现跨域登录。

```
// proxy服务器
server {
    listen       81;
    server_name  www.domain1.com;
    location / {
        proxy_pass   http://www.domain2.com:8080;  #反向代理
        proxy_cookie_domain www.domain2.com www.domain1.com; #修改cookie里域名
        index  index.html index.htm;

        # 当用webpack-dev-server等中间件代理接口访问nignx时，此时无浏览器参与，故没有同源限制，下面的跨域配置可不启用
        add_header Access-Control-Allow-Origin http://www.domain1.com;  #当前端只跨域不带cookie时，可为*
        add_header Access-Control-Allow-Credentials true;
    }
}
```

**⑦window.name + iframe**

window.name属性的独特之处：name值在不同的页面（甚至不同域名）加载后依旧存在，并且可以支持非常长的 name 值（2MB）。

```
//其中a.html和b.html是同域的，都是http://localhost:3000;而c.html是http://localhost:4000
// a.html(http://localhost:3000/b.html)
<iframe src="http://localhost:4000/c.html" frameborder="0" onload="load()" id="iframe"></iframe>
<script>
    let first = true
    // onload事件会触发2次，第1次加载跨域页，并留存数据于window.name
    function load() {
      if(first){
      // 第1次onload(跨域页)成功后，切换到同域代理页面
        let iframe = document.getElementById('iframe');
        iframe.src = 'http://localhost:3000/b.html';
        first = false;
      }else{
      // 第2次onload(同域b.html页)成功后，读取同域window.name中数据
        console.log(iframe.contentWindow.name);
      }
    }
</script>
#b.html为中间代理页，与a.html同域，内容为空。
 // c.html(http://localhost:4000/c.html)
  <script>
    window.name = '我不爱你'  
  </script>
```

总结：**通过iframe的src属性由外域转向本地域**，跨域数据即由iframe的window.name从外域传递到本地域。这个就巧妙地绕过了浏览器的跨域访问限制，但同时它又是安全操作。

**⑧location.hash + iframe**

实现原理： a.html欲与c.html跨域相互通信，通过中间页b.html来实现。 三个页面，不同域之间利用iframe的location.hash传值，相同域之间直接js访问来通信。

具体实现步骤：一开始a.html给c.html传一个hash值，然后c.html收到hash值后，再把hash值传递给b.html，最后b.html将结果放到a.html的hash值中。 同样的，a.html和b.html是同域的，都是`http://localhost:3000`;而c.html是`http://localhost:4000`

```
 // a.html
  <iframe src="http://localhost:4000/c.html#iloveyou"></iframe>
  <script>
    window.onhashchange = function () { //检测hash的变化
      console.log(location.hash);
    }
  </script>
 // b.html
  <script>
    window.parent.parent.location.hash = location.hash 
    //b.html将结果放到a.html的hash值中，b.html可通过parent.parent访问a.html页面
  </script>
 // c.html
 console.log(location.hash);
  let iframe = document.createElement('iframe');
  iframe.src = 'http://localhost:3000/b.html#idontloveyou';
  document.body.appendChild(iframe);
```

**⑨document.domain + iframe**

**该方式只能用于二级域名相同的情况下，比如 a.test.com 和 b.test.com 适用于该方式**。只需要给页面添加 `document.domain ='test.com'` 表示二级域名都相同就可以实现跨域。

实现原理：两个页面都通过js强制设置document.domain为基础主域，就实现了同域。

```
//页面a.zf1.cn:3000/a.html获取页面b.zf1.cn:3000/b.html中a的值

// a.html
<body>
 	helloa
  		<iframe src="http://b.zf1.cn:3000/b.html" frameborder="0" onload="load()" id="frame"></iframe>
  		<script>
    			document.domain = 'zf1.cn'
    			function load() {
      				console.log(frame.contentWindow.a);
    			}
  		</script>
</body>


// b.html
<body>
   	hellob
   	<script>
     	document.domain = 'zf1.cn'
     	var a = 100;
   	</script>
</body>
```

**总结：**

**CORS支持所有类型的HTTP请求，是跨域HTTP请求的根本解决方案**；

**JSONP只支持GET请求**，JSONP的优势在于支持老式浏览器，以及可以向不支持CORS的网站请求数据。

不管是Node中间件代理还是nginx反向代理，主要是通过**同源策略对服务器不加限制**。

注：日常工作中，用得比较多的跨域方案是cors和nginx反向代理

### 如何实现浏览器多个标签页tab之间通信

跨域的如上，同源不跨域的方法如下：

**1.websocket通讯**：WebSocket是HTML5新增的协议，它的目的是在浏览器和服务器之间建立一个不受限的双向通信的通道，比如说，服务器可以在任意时刻发送消息给浏览器。

首先，浏览器用`wss://xxx`创建WebSocket连接时，会先通过HTTPS创建安全的连接，然后，该HTTPS连接升级为WebSocket连接，底层通信走的仍然是安全的SSL/TLS协议。WebSocket连接必须由浏览器发起，**特点**：

（1）建立在 TCP 协议之上，服务器端的实现比较容易。

（2）与 HTTP 协议有着良好的兼容性。默认端口也是80和443，并且握手阶段采用 HTTP 协议，因此握手时不容易屏蔽，能通过各种 HTTP 代理服务器。

（3）数据格式比较轻量，性能开销小，通信高效。

（4）可以发送文本，也可以发送二进制数据。

（5）没有同源限制，客户端可以与任意服务器通信。

（6）协议标识符是`ws`（如果加密，则为`wss`），服务器网址就是 URL。

**为什么传统的HTTP协议不能做到WebSocket实现的功能？**这是因为HTTP协议是一个请求－响应协议，请求必须先由浏览器发给服务器，服务器才能响应这个请求，再把数据发送给浏览器。

**2.定时器setInterval+cookie**：①在页面A设置一个使用 `setInterval` 定时器不断刷新，检查 `Cookies` 的值是否发生变化，如果变化就进行刷新的操作。②由于 `Cookies` 是在同域可读的，所以在页面 B 审核的时候改变 `Cookies` 的值，页面 A 自然是可以拿到的。

**3.使用localstorage**：localstorage是浏览器多个标签共用的存储空间，所以可以用来实现多标签之间的通信(ps：session是会话级的存储空间，每个标签页都是单独的）。直接在window对象上添加监听即可：

```
window.onstorage = (e) => {console.log(e)}
// 或者这样
window.addEventListener('storage', (e) => console.log(e))
```

onstorage以及storage事件，针对都是**非当前页面**对localStorage进行修改时才会触发，当前页面修改localStorage不会触发监听函数。然后就是在对原有的数据的值进行修改时才会触发，比如原本已经有一个key会a值为b的localStorage，你再执行：`localStorage.setItem('a', 'b')`代码，同样是不会触发监听函数的。

**4.html5浏览器的新特性SharedWorker**：普通的webworker直接使用`new Worker()`即可创建，这种webworker是**当前页面**专有的。然后还有种共享worker(SharedWorker)，这种是可以多个标签页、iframe共同使用的。

### 浏览器中跨域创建cookie的问题

问题描述：当提交一个请求到www.b.com这个域时，后台尝试在响应中绑定cookie信息，以告知浏览器去保存这个cookie,但是**默认情况下，浏览器是不会去为你创建cookie的**，具体现象就是你发现在响应中已经有set-cookie的响应头了并且有值，而且浏览器也会有信息显示已接收到cookie了，但是就是在cookie中找不到。没错，该现象就是因为你是跨域提交的创建cookie的请求。**ajax发送跨域请求的时候默认是不会携带cookie的**。

**解决方案**：**前台要配置一个ajax参数：xhrFields:{withCredentials:true}，后台要在响应头中绑定”Access-Control-ALLOW-Credentials”,值为”true”**

 前台要配置一个ajax参数，使用到一个`xmlHttpRequest对象的属性xhrFields`，该属性是一个用来配置xhr对象的键值对，比如在跨域请求有需要的时候设置`withCredentials:true`；

 该属性是告诉浏览器，**1、允许创建来自不同域的cookie信息**；**2、每次的跨域请求都允许带上该cookie信息**

该配置项还**需要后台的允许**才有效，后台如果允许浏览器发送带凭据的请求，那么会在**响应头**中带上`"Access-Control-ALLOW-Credentials"`,值为”true”。

### 2. 有哪几种存储方式？有什么不同？

`cookie`、`localStorage`、`sessionStorage`；

相同点：都保存在浏览器端；

不同点：

**①传递方式不同**

​	`cookie`数据始终在**同源的http请求中携带**（即使不需要），即`cookie`在浏览器和服务器间来回传递。

​	`sessionStorage`和`localStorage`不会自动把数据发给服务器，**仅在本地保存**。

**②数据大小不同**

​	（`cookie`数据还有路径（path）的概念，可以限制cookie只属于某个路径下。） 	存储大小限制也不同，cookie数据**不能超过4k**，同时因为每次http请求都会携带`cookie`，所以cookie只适合保存很小的数据，如会话标识。

​	`sessionStorage`和`localStorage` 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。

**③数据有效期不同**

​	`sessionStorage`：仅在当前**浏览器窗口关闭前有效**，自然也就不可能持久保持；

​	`localStorage`：**始终有效**，窗口或浏览器关闭也一直保存，因此用作持久数据；

​	`cookie`只在设置的**cookie过期时间之前**一直有效，即使窗口或浏览器关闭。

**④作用域不同**

​	`sessionStorage`**不在不同的浏览器窗口中共享**，即使是同一个页面；

​	`localStorage `在所有**同源窗口中都是共享**的；

​	`cookie`也是在所有**同源窗口中都是共享**的。

### 3.点击按钮进行数据请求，怎么实现按序执行请求？

问：点击页面上一个按钮发送两个ajax请求，其中一个请求会不会等待另一个请求执行完毕之后再执行？

答：不会，这两个异步请求会同时发送，执行的快与慢是看响应的数据量的大小及后台逻辑的复杂程度。

问：怎么让它们按序执行？

答：两种方案：

1. Ajax2()方法的执行放到Ajax1()的success**回调函数**的最后一行。
2. Ajax1()的异步请求方法中，增加一个回调函数 ：**complete : Ajax2**

### 4. jQuery和Vue使用起来有什么区别？

 从jquery到vue或者说是到mvvm的转变则是一个思想想的转变，是将原有的直接操作dom的思想转变到操作数据上去。

 从技术角度讲，Vue.js 专注于 MVVM 模型的 ViewModel 层。它通过双向数据绑定把 View 层和 Model 层连接了起来，通过对数据的操作就可以完成对页面视图的渲染。

 jQuery是使用选择器（$）**选取DOM对象**，对其进行赋值、取值、事件绑定等操作，和原生的区别只在于可以更方便的选取和操作DOM对象，其数据和界面是在一起的。

 Vue则是通过Vue对象将数据和View层分离开来。**对数据进行操作**不再需要引用相应的DOM对象，通过Vue对象这个vm实现相互的绑定。

 vue**适用的场景**：复杂数据操作的后台页面，表单填写页面；vue侧重数据绑定；

　　jquery**适用的场景**：比如说一些html5的动画页面，一些需要js来操作页面样式的页面；jquery侧重样式操作，动画效果等；

### 5.cookie和session了解吗？

`cookie`和`sessiom`是两种**保持会话**状态的方法。

​	cookie就是指客户端在向服务端发起请求的时候，服务端会在进行response的时候给当前客户端的一小段文本信息，并保存在当前的客户端的浏览器中，这一小段cookie文本信息也就是这个客户端去访问服务端的通行证，有了这个通行证，以后当这个客户端再去访问服务端的时候，服务端便知道是谁拿着通行证去进行访问了。

​	session和cookie的功能类似，也是一种保持会话状态的方式，在用户使用浏览器发起会话时，服务器会为每一个用户浏览器提供一个单独的session对象来保存用户的数据，并将它保存在服务端，而当用户访问其他web资源的时候，则可以从保存用户数据的session对象中把用户数据抽取出来并进行访问。

**区别**：

1. cookie的用户数据是保存在**用户浏览器**的cookie中的；

session的用户数据是保存在**服务器为用户浏览器单独创建的session对象**中的。

1. 数据的读取和调用，cookie可以采用request.getCookies这种方法；

   session则可以用request.Session的方法。

2. 安全性，cookie是存储在**用户浏览器**中的；

   而session是**存储在服务器**上的，所以session比cookoe要相对安全；

### 30. npm中的工具了解过吗？（yarn）

**npm就是JavaScript的包管理工具。**npm主要用来下载，安装，管理第三方模块。

创建一个包描述文件：`npm init [-y]`

查看包的信息 `npm info <package-name>`

查看包的版本信息 `npm info <package-name> versions`

安装指定的包：`npm install <package-name>` 默认会安装在当前目录下的 node_modules 目录下，如果 node_modules 不存在，则会自动创建。 本地安装包，如果包里有可执行文件，则npm会把可执行文件安装到 node_modules/.bin 目录下。

安装指定版本的包：`npm install <package-name>@<version>`

安装包并记录依赖，会在 package.json 中 dependencies 属性记录依赖`npm install <package-name> --save`

卸载包：`npm uninstall <package-name>`

更新包：`npm update <package-name>`

全局安装包，把包安装在全局目录，供所有项目使用:`npm install <package-name> -g` 全局安装包，如果包里有可执行文件，则npm会把可执行文件安装到 node_modules 上一级目录中。

查看全局目录：`npm root -g`

修改全局目录的路径：`npm config set prefix "新路径"` 默认情况下全局安装的包不能直接在项目中加载，如果要直接加载，需要在系统环境变量中添加一个名为 NODE_PATH 的变量，值为全局安装目录下 node_modules 位置。

查看npm配置 `npm config list`

### 7. Node.js了解吗？

​	根据官方文档可以知道，node就是一个给予谷歌v8引擎的一个javascript的运行时，可以理解为**运行js的一个虚拟机**。他使用的是一个事件驱动，非阻塞I/O模型 ，他是**将js的运行环境搬到了服务器端**，和客户端没有一点关系。是一个纯服务端的东西，node只是**为js提供了一个平台**。

　　node里面其实还分了两块，一是封装了v8引擎，目的是为了执行es（如定义变量，定义函数等），另外一个提供了大量的工具库，是帮助node实现各种功能的，提供了一些以前js的环境办不到的事情，比如文件操作，网络操作，操作系统的操作。

​	既然node是一个平台（所谓的平台就是用来运行特定语言的），也就意味着node是用来运行语言的，那么java也是语言，node能运行java吗？据nodejs创始人Ryan Dahl回忆，他最初是选择了Ruby这门语言，但是Ruby这门语言的虚拟机效率不怎么样最终放弃了，按照这种思路，貌似node将java的虚拟机集成进来应该可以运行java，但node作者最终选择了javascript。

　　这样js就实现了在服务端运行的可能，js运行在node平台上（分为v8部分，用来执行es，和大量的工具库组件（API）称之为libuv，提供了以前js的环境办不到的事，如文件操作，网络操作等等）。

用途：

​	（1）node可以**接受客户端用户的所有请求**，并且能够快速的给出响应，因此node可以用来做网站。

　　（2）node可以作为一个**中间层来来分发调用数据接口**，比如有一个网站数据是有java提供的，我们可以让node作为一个中间层，来接受用户的请求，然后**通过node来调用java数据接口**，获取到数据后直接在node层面做html的封装，然后将渲染好的页面直接给用户。为什么要这样做，直接请求java接口不行吗，这是因为node被称之为**高性能的web服务器**，在**并发和抗压**方面都比传统的平台要好很多，因此这样一包装可以极大的减轻服务器的开发。

　　通过上面的两点，可以总结出，node在web中要么从前端页面到后端服务全包了，一个是只做其中的一点。

　　**一言以蔽之，node就是一个javascript的运行环境（平台），他不是一门语言，也不是javascript的框架。可以用来开发服务端应用程序，web系统。其特点是体积小，快速，高性能。**

### 8.城市搜索和区块联动用的组件怎么实现的？

城市搜索功能是将input输入的内容，绑定到变量keyword上面，然后用watch监听这个变量，一旦变量变化，就用变量执行indexOf的方法去便利城市的name和value值，将得到的值push进入数组，然后将数组遍历显示在ul>li里面。

```
 watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
	<div
      class="search-content"
      ref="search"
      v-show="keyword"
    >
      <ul>
        <li
          class="search-item border-bottom"
          v-for="item of list"
          :key="item.id"
          @click="handleCityClick(item.name)"
        >
          
        </li>
        <li class="search-item border-bottom" v-show="hasNoData">
          没有找到匹配数据
        </li>
      </ul>
    </div>
```

区块联动的组件

给每个字母都绑定ref，同时绑定方法，点击的时候；移动的时候，根据高度来进行区域块的联动

```
<template>
  <ul class="list">
    <li
      class="item"
      v-for="item of letters"
      :key="item"
      :ref="item"
      @touchstart.prevent="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTouchEnd"
      @click="handleLetterClick"
    >
      
    </li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    //点击字母的时候，将点击得到的内容字母向父级传输，触发change的方法
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    //手指移动的时候，节流一下，同时也是触发父级的change，将手指滑动的内容传递
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - this.startY) / 20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>
```

### 9.用Ajax的时候，get和post有什么区别？

​	GET和POST都是HTTP协议中的两种发送请求的办法，都是基于TCP/IP。

​	get 和post 安全等级是同级别的，不要说安全区别，都不安全，get有数据缓存的问题，清缓存query需要加时间戳，post就不会有这个问题。（站友分享思路）

| GET                                    | POST                               |
| :------------------------------------- | :--------------------------------- |
| 向服务器获取指定资源                   | 向服务器提交数据，数据放在请求体里 |
| **把参数包含在`URL`中**                | 通过`request body`传递参数         |
| 有长度限制，2kB                        | 没有限制                           |
| 只能进行`URL`编码                      | 支持多种编码方式                   |
| 在浏览器**回退时是无害的**             | 在浏览器回退时，POST会再次提交请求 |
| GET请求会被浏览器**主动cache**         | POST不会缓存，除非手动设置         |
| 请求参数会被完整保留在浏览器历史记录里 | 参数不会被保留                     |

### 10.bootstrap中的栏栅一行有12个，是怎么做到的？

​	总共有**五个栅格等级**，每个响应式分界点隔出一个等级：特小`.col-`、小`.col-sm-`、中 `.col-md-`、大`.col-lg-`、特大`.col-xl-`。

​	使用的row行必须包裹在`container`和`container-fluid`下，外部容器一个是`container`，一个是`container-fluid`，第一个**`container`是固定宽度，居中在网页中间**，第二个**`container-fluid`是百分比宽度，宽度为100%**，根据情况我们可以选择不同的容器。

![img](https://codingwithalice.github.io/img/assets_2019/container.png)

**工作原理**：

​	栅格系统提供了**内容居中**、**水平填充**网页内容的方法，`.container`实现固定的宽度并居中呈现，`.container-fluid`实现全宽度，并和其它网格实现对齐。

​	行(.row)是列(.col-*)的横向组合和父容器，**每列都有水平的padding值**，用于控制列与列之间的间隔，同时在负边距的行上抵消，从而实现列中的所有内容在视觉上是左侧对齐的体验。

​	.row上带有`margin-left: -15px;margin-right: -15px;`属性，你可以在.row上上定义`.no-gutters`属性，从而消除这个属性，使页面不会**额外宽出30px**，即`<div class="row no-gutters"...`。

​	`.col-*`的`width`属性(即列宽)是**用百分比来表现**和定义的，所以它们总是流式的，其尺寸大小受父元素的定义影响。

|                                    | 超小屏幕（新增规格）<576px | 小屏幕 次小屏≥576px | 中等屏幕 窄屏≥768px | 大屏幕 桌面显示器≥992px | 超大桌面 大桌面显示器≥1200px |
| :--------------------------------- | :------------------------- | :------------------ | :------------------ | :---------------------- | :--------------------------- |
| container最大宽度                  | None（auto）               | 540px               | 720px               | 960px                   | 1140px                       |
| 类前缀                             | .col-                      | .col-sm-            | .col-md-            | .col-lg-                | .col-xl-                     |
| 列数                               | 12列                       | 12列                | 12列                | 12列                    | 12列                         |
| Gutter width（都是每列两侧各15px） | 30px                       | 30px                | 30px                | 30px                    | 30px                         |
| 列间隙（都是每列两侧各15px）       | 30px                       | 30px                | 30px                | 30px                    | 30px                         |
| 都可嵌套、可排序                   |                            |                     |                     |                         |                              |

### 11.轮播图实现的时候是怎么考虑的？

四种方式实现：

​	swiper插件实现轮播图；

​	JS实现轮播图；

​	jQuery实现轮播图；

​	css3实现轮播图；

```
		// 1. 克隆元素
        ul.appendChild(ul.children[0].cloneNode(true));
        // 2.创建ol 和li
        var ol = document.createElement("ol");//创建ol元素
        scroll.appendChild(ol);// 把ol放到scroll盒子里面去
        for (var i=0;i<ulList.length-1;i++) {
            var li = document.createElement("li");// 创建li元素
            li.innerHTML = i + 1;// 给li里面添加文字  1 2 3 4 5
            ol.appendChild(li);// 将li元素添加到ol里面
        }
        ol.children[0].className = "current";
// ol中的第一个li背景色为purple现无缝滚动就需要多一张图片才行，即克隆第一张图片，放到最后面
//动画函数：
		// 动画函数的第一个参数，代表动画对象；第二个参数代表动量
        // 让图片做匀速运动，匀速动画的原理是:当前的位置 + 速度,即 offsetLeft + speed
        function animate(obj,target){
            // 首先清除掉定时器
            clearInterval(obj.timer);
            // 用来判断 是+ 还是 -  即说明向左走还是向右走
            var speed = obj.offsetLeft < target ? 15 : -15;
            obj.timer = setInterval(function(){
                var result = target - obj.offsetLeft;//它们的差值不会超过speed
                obj.style.left = obj.offsetLeft + speed + "px";
                // 有可能有小数的存在，所以在这里要做个判断             
                if (Math.abs(result) <= Math.abs(speed)) {
                    clearInterval(obj.timer);
                    obj.style.left = target + "px";
                }
            },10);
        }
//定时器函数：
		var timer = null; 	// 轮播图的定时器
        var key = 0;		// 控制播放的张数
        var circle = 0;		// 控制小圆点

        timer = setInterval(autoplay,1000);// 自动轮播
        function autoplay(){
/*自动轮播时,要对播放的张数key进行一个判断,如果播放的张数超过ulLis.length-1,就要重头开始播放.  
		因为我们克隆了第一张并将其放在最后面,所以我们要从第二张图片开始播放*/
            key++; 						// 先++
            if(key > ulLis.length-1){	// 后判断
                ul.style.left = 0; 		// 迅速调回
                key = 1; 				// 因为第6张是第一张，所以播放的时候是从第2张开始播放
            }
// 动画部分
            animate(ul,-key*liWidth);

// 小圆点circle，当显示第几张图片是，对应的小圆点的颜色也发生变化 
            /*同理,对小圆点也要有一个判断*/
            circle++;
            if (circle > olLis.length-1) {
                circle = 0;
            }
            // 小圆点颜色发生变化
            for (var i = 0 ; i < olLis.length;i++) {
                // 先清除掉所用的小圆点类名
                olLis[i].className = ""; 
            }
            // 给当前的小圆点 添加一个类名
            olLis[circle].className = "current";

        }
```

### 12.前端性能优化的方法，举例说明

**①内容方面**

**减少HTTP请求次数**（使用精灵图） **减少DOM操作** **减少DNS查询**：当客户端DNS缓存（浏览器和操作系统）缓存为空时，DNS查找的数量与要加载的Web页面中唯一主机名的数量相同，包括页面URL、脚本、样式表、图片、Flash对象等的主机名。减少主机名的 数量就可以减少DNS查找的数量。减少唯一主机名的数量会潜在减少页面中并行下载的数量（HTTP 1.1规范建议从每个主机名并行下载两个组件，但实际上可以多个），这样减少主机名和并行下载的方案会产生矛盾，需要大家自己权衡。建议将组件放到至少两个但不多于4个主机名下，减少DNS查找的同时也允许高度并行下载。

**使用Ajax 可缓存**：POST的请求，是不可以在客户端缓存的，每次请求都需要发送给服务器进行处理，每次都会返回状态码200。（可以在服务器端对数据进行缓存，以便提高处理速度）。GET的请求，是可以（而且默认）在客户端进行缓存的，除非指定了不同的地址，否则同一个地址的AJAX请求，不会重复在服务器执行，而是返回304。

**②css方面**

把css样式HTML代码页的头部，防止白屏 从页面中分离css代码，从外部引入 压缩代码 不要使用@import 避免css表达式`width: expression(func(),document.body.clientWidth > 400 ? "400px" : "auto");`

**③js方面**

脚本放到HTML代码页底部

从页面中分离js代码，从外部引入。

压缩代码 减少对DOM的访问 移除重复的脚本

**④图片方面**

优化图片（少用图片用css3新特性代替，使用矢量图代替位图） 矢量图：图标字体。 位图：GIF、JPG、PNG 不要在HTML中使用缩放图片 使用恰当的图片格式 按照HTTP协议设置合理的缓存 用css或js实现预加载 WebP图片格式能给前端带来优化 WebP格式：谷歌开发一种旨在加快图片加载速度的图片格式

```
(function(){
	try{
		console.log(a);
		
		var a="a";
		console.log(a);
		b();
		c(); 
		
		function b(){
			console.log("b");
		}
		var c=function(){
			console.log("c");
		}
		console.log("d")
        
        }
})
```

### 13.SEO搜索引擎优化有哪些方法？

1.创建唯一且准确的**网页标题` <title>`**

```
<title>前端搜索引擎优化的技巧</title>
```

2.使用 **`<meta>` 的 `keywords` 元数据**来提炼网页重要关键字，以及 `description` 元数据准确总结网页内容。

```
<meta name='keywords' content='SEO,title,meta,语义化,alt'>
<meta name='description' content='介绍搜索引擎优化的技巧:语义化标签、img的alt属性等。'>
```

3.使用**语义化元素**：`<em>` 或 `<strong>`

4.利用**` <img> `中的`alt` 属性**

5.设置`rel='nofollow' `忽略跟踪

6.尽量让结构（HTML）、表现（CSS）及行为（JavaScript）**三者分离**。如果在一个 HTML 页面中，编写大量的 CSS 样式或脚本，会拖慢其加载速度，此外，如果不为 `<img>` 定义宽高，那么会引起页面重新渲染，同样也会影响加载速度。一旦加载超时，“蜘蛛”就会放弃爬取。如果这个 HTML 文档内容比较独特丰富（合理插入图片说明）等，会被认为质量较高符合用户需求，从而提高 SEO 的排名。

### 15、学过哪些基础框架？

前端框架：Vue、AngularJS、React （还有其他的话请补充，只列主流的）

界面框架/UI框架：Bootstrap

### 16、jQuery中绑定事件用的on和bind有什么区别？

```
bind(type, [data], fn)//解绑用unbind
on(type,[selector],[data],fn)//解绑用off
```

区别在于：是否支持selector这个参数值。

​	由于javascript的**事件冒泡特性**，如果我们在父元素上注册了一个事件处理函数，当子元素上发生这个事件的时候，父元素上的事件处理函数也会被触发。**如果使用on的时候，不设置selector，那么on与bind就没有区别**了。

```
<div id="parent">
	<input type="button" value="a" id="a"/>
	<input type="button" value="b" id="b"/>
</div>
/*点击a的时候触发，点击b的时候不触发*/
$("#parent").on("click","#a",function(){
	alert($(this).attr("id"));
});
```

​	**on()函数的参数selector就是为了在事件冒泡的时候，让父元素能够过滤掉子元素上发生的事件。**如果使用了bind，那么就没有这个能力，子元素上发生的事件一定会触发父元素事件。

bind()、unbind()、on()、off()的几个通性：（这里主要写bind和unbind）

①、**JQuery中事件可以重复绑定，不会覆盖**

```
//点击button1的时候，这2个事件处理函数都会触发
$("#button1").bind("click",function(){	alert("func1");});
$("#button1").bind("click",function(){	alert("func2");});
```

②、**使用bind一次绑定多个事件和处理函数**

```
//多个事件需要注册相同的处理函数
$("#button1").bind("mousedown mouseup",function(){
	console.log(11);
});
//如果每个事件的处理函数不同，可以用json对象
$("#button1").bind(
	{
		"mousedown":function(){
			console.log("mousedown");
		},
		"mouseup":function(){
			console.log("mouseup");
		}
	}
);
```

③、**传递event对象和自定义参数**

```
//如果我们指定了自定义的参数，那么JQuery会将它放在事件对象的data属性中，即通过eventObject.data就能够拿到我们传递的参数值
$("#button1").bind("click", {name:"aty"}, function(eventObject){  
    alert("params=" + eventObject.data.name);  
});
```

④、**事件取消的三种形式**

unbind用来取消之前通过bind绑定的事件处理函数，总的来说有三种形式：**取消所有事件**、**取消某种类型的事件**、**取消某种类型下的某个事件处理函数**。

```
$("#button1").unbind()//取消button1上所有已经绑定的事件处理函数。
$("#button1").unbind("click")//只取消button1上绑定的click类型的事件处理函数。
```

取消某种类型下的某个事件处理函数：

```
/容易犯的错误写法
$("#button1").bind("click",function(eventObj){console.log("click1");}); 
$("#button1").bind("click",function(eventObj){console.log("click2");}); 

// 这种写法是错误的，虽然用的匿名函数的功能相同，但这两个函数不是同一个，它们占用的是不同的内存空间
$("#button1").unbind("click",function(eventObj){console.log("click2");});
/正确写法
$("#button1").bind("click",func1); 
$("#button1").bind("click",func2); 
// 这种做法不允许使用匿名函数，我们不得不暴露全局的函数，JQuery提供了事件命名空间机制
$("#button1").unbind("click",func2); 
function func1(){console.log("click1");}
function func2(){console.log("click2");}
```

⑤、**事件命名空间**

​	事件类型后面**以点语法附加一个别名**，以便引用事件，如”click.a”，其中”a”就是click当前事件类型的别名，即事件命名空间。

```
$("#button1").bind("click.a",function(eventObj){console.log("click1");}); 
$("#button1").bind("click.b",function(eventObj){console.log("click2");}); 
 
// 使用命名空间，能够以一种更优雅的方式取消某种事件类型下的某个事件处理函数
$("#button1").unbind("click.a");
```

能够按照命名空间来取消事件`$("#button1").unbind(".a");`

### 17.从输入URL到页面加载完成，发生了什么：segmentfault上面有篇博客：[从输入url到页面展现发生了什么？](https://segmentfault.com/a/1190000013522717)

域名解析 –>

根据地址栏输入的地址向[DNS（Domain Name System）](https://zh.wikipedia.org/wiki/域名系统)查询IP –>

通过IP向服务器发起TCP连接 –>

发起TCP的3次握手 –>

建立TCP连接后发起http请求 –>

服务器响应http请求，浏览器得到html代码 –>

浏览器解析html代码，并请求html代码中的资源（如js、css、图片等） –>

浏览器对页面进行渲染呈现给用户

### 18.事件委托是什么？

将事件的处理程序绑定给一个父级元素，当任何子节点触发了匹配的父级元素绑定的事件，即可触发父级节点的处理程序，这就是 **事件委托** 。

事件委托是通过事件 ”冒泡“ 来用单个父节点而非多个子节点响应 [UI Events](https://www.w3.org/TR/uievents/) 的技巧。

**优点：**

- **减少事件绑定**，事件委托将很多子元素的事件绑定都集中到一个通用的父元素，使得**动态创建和移除的元素**更加方便，**对于新添加的元素也会有之前的事件**，不需要考虑元素的事件绑定逻辑。假设需要对 <li> 标签进行增加，只管进行操作就行，不用增加元素的 “onclick” 事件。
- **减少事件监听使用的内存**，这可能对那些经常重新加载的小页面效果不明显，但是对需要长时间运行的应用很重要。因为当元素被从 DOM 中移除之后很难追踪它对内存的使用，造成内存泄露，这是由元素的事件绑定造成的。有了事件委托，在移除子元素之后不用担心没有解除绑定事件。

**那什么样的事件可以用事件委托，什么样的事件不可以用呢？**

适合用事件委托的事件：click，mousedown，mouseup，keydown，keyup，keypress。值得注意的是，mouseover和mouseout虽然也有事件冒泡，但是处理它们的时候需要特别的注意，因为需要经常计算它们的位置，处理起来不太容易。

不适合的就有很多了，举个例子，mousemove，每次都要计算它的位置，非常不好把控，在不如说focus，blur之类的，本身就没用冒泡的特性，自然就不能用事件委托了。

```
<ul id='ul'>
    <li>111111</li>
    <li>222222</li>
    <li>333333</li>
 </ul>
 <button id='button'>添加元素</button>
window.onload = function(){
      let Ul = document.getElementById('ul');
      let Li = oUl.getElementsByTagName('li');
      let but = document.getElementById('button');
      let now = 3;
      // 事件源：event对象，不管在哪个事件中，只要你操作的哪个元素就是事件源
      // ie：window.event.srcElement
      // 标准：event.target
      //Event对象提供了一个属性叫target，可以返回事件的目标节点，我们成为事件源，也就是说，target就可以表示为当前的事件操作的dom，但是不是真正操作dom，当然，这个是有兼容性的，标准浏览器用ev.target，IE浏览器用event.srcElement，此时只是获取了当前节点的位置，并不知道是什么节点名称，这里我们用nodeName来获取具体是什么标签名，这个返回的是一个大写的，我们需要转成小写再做比较（习惯问题）
      oUl.onmouseover = function(e){
        let ev = e || window.event;
        let target = ev.target || ev.srcElement;
        if(target.nodeName.toLowerCase() == 'li'){
          target.style.background = 'red';
        }
      }
      oUl.onmouseout = function(e){
        let ev = e || window.event;
        let target = ev.target || ev.srcElement;
        if(target.nodeName.toLowerCase() == 'li'){
          target.style.background = '';
        }
      }
      but.onclick = function(){
        now ++;
        let newLi = document.createElement('li');
        newLi.innerHTML = 111111 * now;
        Ul.appendChild(newLi);
      }
    }
```

### 19.前端框架Vue、angular、React的优点和缺点

其实Vue.js不是一个框架，因为它只聚焦视图层，是一个构建数据驱动的Web界面的库。

Vue.js通过简单的API（应用程序编程接口）提供高效的数据绑定和灵活的组件系统。

**Vue.js的特性如下：**

```
1.轻量级的框架
2.双向数据绑定
3.指令
4.插件化
```

**优点：**

```
1. 简单：官方文档很清晰，比 Angular 简单易学。
2. 快速：异步批处理方式更新 DOM。
3. 组合：用解耦的、可复用的组件组合你的应用程序。
4. 紧凑：~18kb min+gzip，且无依赖。
5. 强大：表达式 & 无需声明依赖的可推导属性 (computed properties)。
6. 对模块友好：可以通过 NPM、Bower 或 Duo 安装，不强迫你所有的代码都遵循 Angular 的各种规定，使用场景更加灵活。
```

**缺点**

```
1. 新生儿：Vue.js是一个新的项目，没有angular那么成熟。
2. 影响度不是很大：google了一下，有关于Vue.js多样性或者说丰富性少于其他一些有名的库。
3. 不支持IE8：
```

angularJS是一款优秀的前端JS框架，已经被用于Google的多款产品当中。

**angularJS的特性如下：**

```
1.良好的应用程序结构
2.双向数据绑定
3.指令
4.HTML模板
5.可嵌入、注入和测试
```

**优点：**

```
1. 模板功能强大丰富，自带了极其丰富的angular指令。
2. 是一个比较完善的前端框架，包含服务，模板，数据双向绑定，模块化，路由，过滤器，依赖注入等所有功能；
3. 自定义指令，自定义指令后可以在项目中多次使用。
4. ng模块化比较大胆的引入了Java的一些东西（依赖注入），能够很容易的写出可复用的代码，对于敏捷开发的团队来说非常有帮助。
5. angularjs是互联网巨人谷歌开发，这也意味着他有一个坚实的基础和社区支持。
```

**缺点：**

```
1. angular 入门很容易 但深入后概念很多, 学习中较难理解.
2. 文档例子非常少, 官方的文档基本只写了api, 一个例子都没有, 很多时候具体怎么用都是google来的, 或直接问misko,angular的作者.
3. 对IE6/7 兼容不算特别好, 就是可以用jQuery自己手写代码解决一些.
4. 指令的应用的最佳实践教程少, angular其实很灵活, 如果不看一些作者的使用原则,很容易写出 四不像的代码, 例如js中还是像jQuery的思想有很多dom操作.
5. DI 依赖注入 如果代码压缩需要显示声明.
```

React主要用于构建UI。你可以在React里传递多种类型的参数，如声明代码，帮助你渲染出UI、也可以是静态的HTML DOM元素、也可以传递动态变量、甚至是可交互的应用组件。

**React特性如下：**

```
1.声明式设计：React采用声明范式，可以轻松描述应用。
2.高效：React通过对DOM的模拟，最大限度地减少与DOM的交互。
3.灵活：React可以与已知的库或框架很好地配合。
```

**优点：**

```
1. 速度快：在UI渲染过程中，React通过在虚拟DOM中的微操作来实现对实际DOM的局部更新。
2. 跨浏览器兼容：虚拟DOM帮助我们解决了跨浏览器问题，它为我们提供了标准化的API，甚至在IE8中都是没问题的。
3. 模块化：为你程序编写独立的模块化UI组件，这样当某个或某些组件出现问题是，可以方便地进行隔离。
4. 单向数据流：Flux是一个用于在JavaScript应用中创建单向数据层的[架构](https://link.jianshu.com/?t=http://lib.csdn.net/base/16)，它随着React视图库的开发而被Facebook概念化。
5. 同构、纯粹的javascript：因为搜索引擎的爬虫程序依赖的是服务端响应而不是JavaScript的执行，预渲染你的应用有助于搜索引擎优化。
6. *兼容性好：比如使用RequireJS来加载和打包，而Browserify和Webpack适用于构建大型应用。它们使得那些艰难的任务不再让人望而生畏。
```

**缺点：**

```
React本身只是一个V而已，并不是一个完整的框架，所以如果是大型项目想要一套完整的框架的话，基本都需要加上ReactRouter和Flux才能写大型应用
```

### 20.1有哪些

![1571447049844](https://codingwithalice.github.io/img/assets_2019/1571447049844.png)

### 21.给出一个场景，要求A、B请求执行结束后，再执行C请求，其中A、B请求同时开始，怎么实现：Promise.all

```
async function A(){}
async function B(){}
function C(){}
Promise.all([A(),B()]).then(C)
```

或者

```
const A = async () =>  await 'A';
const B = async () =>  await 'B';
const C = () =>  'C';
(async function All() {
    await Promise.all([A(), B()]);
    C();
})();
```

或者

```
var promise1 = new Promise((resolve, reject) => {
    setTimeout(() => {
        console.log(1);
        resolve()
    }, 0);
});
var promise2 = new Promise((resolve, reject) => {
    setTimeout(() => {
        console.log(2);
        resolve()
    }, 0);
});
Promise.all([promise1, promise2]).then(function(res) {
  console.log(3)
});
```

或者

```
var index = 0
function C(){
    console.log(3);
}
setTimeout(() => {
    console.log(1);
    index++;
    if(index === 2){
        C()
    }
}, 0);
setTimeout(() => {
    console.log(2);
    index++;
    if(index === 2){
        C()
    }
}, 0);
```

### 22.简单的数值运算

```
1+'2'+'2'="122"
1+ +'2'+'2'="32"
1+ -'1'+'2'="02"
'A'-'B'+'2'="NaN2"
'A'-'B'+2=NaN
```

1. Canvas绘图；

2. Ajax遇到拦截器，请求数据要重新处理怎么做？

3. vue-cli如何使用json数据模拟？

4. bootstrap用了哪些，jQuery用了哪些，css选择器有哪几种，有哪些优先级，+ > 分别表示什么，子代/后代

5. 项目中轮播图、列表、联动、递归展示使用，后台数据怎么模拟，获取的地址是怎么写的，面试官会详细听，问到代码，甚至会给出一定的意见（v-for改为数组管理），项目的难点在哪里

6. 学习的方法有哪些，《js高级程序设计》中函数重载了解吗

7. eval()函数可以解释由js源代码组成的字符串吗？该函数能用调试工具进行断点调试吗？该函数是js自带的函数，会不会引起安全性问题？该函数动态解释字符串，会存在效率问题吗？

8. 属性document.body.scrolWidth表示网页中滚动条的宽度吗？

9. js或DOM操作方便，浏览器兼容的注意项有哪些

10. Web前端开发常见的安全漏洞

11. 轮播图的实现及后台数据抓取

12. 安全性，在无法使用HTTPS的情况下，局域网如何实现防止报文攻击

13. 列举常用浏览器以及说明其内核

14. 可以通过什么途径查看一个网站所使用的技术

15. react的核心是什么

16. 为什选择`vue+element`这样一个体系搭建系统？有什么吗优点？

17. 公司要求写代码，用js原生仿照发布者订阅者模式写。

18. 写一个左侧导航栏，不能调试，鼠标移动底部变色，参照京东左侧导航栏

19. 虚拟DOM说一下？在生命周期里的对应阶段？

20. 用的前端组件是什么？

21. 问了一下通讯录界面的布局

22. 验证码有写过没

23. npm有学过除简单命令之外的服务构建么？

24. echarts有用过么？WebGL知道么？

25. 数据结构了解多少？数据库呢？

26. es6怎么声明类？继承怎么写？提出是为了解决什么问题？

27. 怎么样去查看内存、性能：性能chrome调试的时候用network的网络选项，内存不清楚

28. react用过吗？讲了一下react和vue之前，jQuery和bootstrap，问学过吗？

29. 数据结构、算法之类的了解吗

30. 实现0.5px横线

31. 盒子模型height

32. 定时器一秒加一次

33. Webscoket（解决痛点）

34. Vue写插件的时候，比较核心的install方法是怎么实现的

35. 我现有项目里面使用的微信开发者工具是比较原生的小程序开发方法，有没有了解过比较新的小程序写法

36. es6中Promise、async await、generator分别是怎么使用的，她给了一个场景：按序分别请求三次数据，前一次调用结束才能开始下一次，怎么写

    我回答：在promise里面，await+请求方法，resolve的时候回调下一个请求

    她说这种性能比较低，链式的结果就是一个常见的回调地狱

37. keep-alive标签的原理是什么？有什么功能？

38. http里面cache-control了解吗？有什么作用？

39. 在页面中的动画，设置一个定时器，间隔一段时间就动一次，考虑性能，以及考虑整个页面的刷新时间，应该设置多长时间？我？？？不知道要问我什么，我说我平常是写死的，500ms

40. 在同源的标签里面要传递数据，会用什么方法？

41. 我回答不考虑安全性就是local storage，websocket也有（这个问题没查过，做笔试的时候做到过，只知道有这个方法，但是不知道怎么用）

42. ajax的原理

43. rem是基于什么原理进行适配的

44. 面向对象的基本特性（3个）

45. 类数组对象是什么

46. 参数系列化

47. z-index的生效前提

48. react生命周期

49. ==和===的区别

50. null和undefined的区别

51. 用typeof bar===‘objec’验证的风险

52. NaN是什么？是什么类型？验证它的函数？

53. this的作用域是什么

54. use strict是什么？

55. 什么是window对象？什么是document对象

56. 替代图片有哪几种

57. MVVM的原理

58. 输入http到渲染到页面，发生了什么

59. 创建一个对象有哪几种方法（字面量、构造函数、工厂模式）

60. 基本数据类型和引用数据类型的区别

61. 箭头函数和普通函数的区别，普通函数this的指向问题

62. set有那些用处？

63. for循环可以用什么代替（reduce）说说reduce

64. js中遍历对象的方法？for in能否遍历出原型对象？

65. created和mounted的区别？

66. vue中v-model的原理？说一下Object.defineProperty上的方法？

67. 知道vue3.0中的proxy么？

68. v-if与v-show computed与watched的区别和应用场景？

69. 浏览器策略–同源策略

70. 写一个函数判断一个字符串回文

71. 写一个方法将多个对象合并成一个对象（大概是这个，当时我理解错了）

72. css写得多不，常用布局

73. vue-router原理

74. 计算机网络中，客户端发送请求到客户端可以怎么发送

75. 用style和.css文件引入css样式有什么不同？分别适用于什么场景？

76. 项目中的公共样式是使用提取出来的单独文件好，还是统一放在style里面好？

77. 使用rem作为手机端适配单位的过程中有没有遇到什么问题？会不会出现用px更好的情况？

78. 什么是http协议？

79. 三次握手中，服务端在发送ACK包+SYN包时做了什么

80. 线程和进程有什么区别

81. 手写一个单向链表

82. vuex请求？原理？

83. vue双向绑定？只知道Object.defineProperty不够

84. 父子传值？vuex、bus，知道eventbus吗？

85. vue生命周期有哪些？destroy用过吗？

86. 手写代码实现一个eventbus。分别实现三种方法listen、trigger、remove

87. 回流和重绘

88. XSS脚本攻击

89. input、onmousedown、onmouseup、click、onfocus之间的区别

90. fetch请求是什么

91. 缓存相关Header

92. node里的事件机制

93. Promise常用API有哪些？

94. await后面跟的是什么？

95. 解释一下es6的Symbol，Symbol解决了什么问题？

96. 介绍一下map和set

97. defineProperty的缺陷？怎么解决这个问题？

98. vuex的工作流程

99. vuex和redux的区别？

100. three.js学得怎么样

101. 学习有关正则表达式的API，例如exec、test





# js相关 面试问题

#### 1. setTimeout输出值的时候，如何实现i按序输出？

```
for(var i=0;i<10;i++){
    setTimeout(function ten(){
            console.log(i);
        },10);
}//输出结果是10个10
```

问：为什么输出的是10个10？

答：JS是一个单线程的解释器，setTimeout本质是间隔一定时间将任务添加到任务队列中。输出的时候for循环作为主线程已经执行完毕，此时作用域中的`i=5`；按序执行10次输出`i`，就会输出10个10；

问：如何输出成按序输出？

答：方法一：

生成一个**立即执行的函数**，将`i`作为参数输入（闭包）

```
for(var i=0;i<10;i++){
    (function(i){
    	setTimeout(function ten(){
            console.log(i);
        },10);
    })(i)
}
```

方法二：用es6中的let来声明变量，相当于**let在每个块级作用域里面都声明了一个变量`i`**

```
for(let i=0;i<10;i++){
    setTimeout(function ten(){
            console.log(i);
        },10);
}
```

方法三：使用`setTimeout`的**第三个参数**

```
for(var i=0;i<10;i++){
    setTimeout(function ten(){
            console.log(i);
        },10,i);
}
```

#### 2. 继承prototype大概是怎么实现的？

实例对象per的构造器constructor是指构造函数Person；

```
console.log(per.constructor==Person);//true
```

实例对象的`_proto_`和构造函数中的**prototype**相等；

```
console.log(per._proto_.constructor==Person.prototype.constructor);//true
```

**原型链**：实例对象使用的属性或者方法，先在实例中查找，找到了则直接使用，找不到则去实例对象的`__proto__`指向的原型对象prototype中找，找到了则使用,找不到则报错。

**实例对象**中有**`_proto_`**这个属性，叫原型，也是一个对象，这个属性是给**浏览器**使用，

不是标准的属性—–>**__proto__**—–>**可以叫**原型对象；

**构造函数**中有**prototype**这个属性，叫原型，也是一个对象，这个属性是给**程序员**使用，

是标准的属性——>**prototype**—>**可以叫**原型对象；

1. **原型继承**核心就是让自定义的构造器的prototype对象**指向**父类构造器生成的对象：

```
//Person是个构造函数，Per是自定义的构造器
function Per(){}
Per.prototype = new Person('Alice');
const person = new Per()//继承父类实例定义的所有属性以及父类构造器原型上的属性
```

1. **借用函数继承**：通过函数对象本身的 `call` 和 `apply` 来显示的指定函数调用时必备的参数；

```
function Per(name){
    Person.call(this,name)//当成了普通函数来使用
}
const person = new Per('Alice')
//只能调用Person中定义的属性和函数，无法调用Person定义在prototype上的属性和方法
```

1. **组合继承（原型链+借用函数）**：[为了解决借用函数无法使用函数原型上的属性和方法]

```
function Per(name){
    Person.call(this,name)//当成了普通函数来使用
}
Per.prototype = new Person('Alice')//这样写，会造成Animal实例化两次，没有自己的原型
//或者
Per.prototype = Person.prototype//这样写，就不会造成多次实例化

const person = new Per('Alice')
```

1. **原型式继承**：提供一个被继承的对象，把这个对象挂在到某个构造函数的**prototype**上，再利用new；

```
function inherit (object) {
  function fn () {} 		// 提供一个函数
  fn.prototype = object ;	// 设置函数的prototype
  return new fn() 			// 返回这个函数实例化出来的对象
}
const person = Person('Alice');
const me=inherit(person);//可以继承peroson对象上所有的方法和属性
```

1. **寄生式继承**
2. **寄生组合式继承**：利用 `Object.create()` 方法

#### 3. js的垃圾回收机制？（摘自红宝书）

1. 离开作用域的值将被自动标记为可以回收，因此将在垃圾收集期间被删除；
2. **“ 标记清除 ”** 是目前最主流的垃圾收集算法，这种算法的思想是给当前不使用的值加上标记，然后再回收其内存（当变量进入环境时，将变量标记为“进入环境”。当变量离开环境时，将其标记为“离开环境”，标记“离开环境”的就回收内存）；
3. 另一种垃圾收集算法是 **“ 引用计数 ”** ，这种算法的思想是跟踪记录所有值被引用的次数。`JavaScript`引擎目前都不再使用这种算法；但在 IE 中访问非原生`JavaScript`对象（如`DOM`元素）时，这种算法仍然可能会导致问题；
4. 当代码中存在循环引用现象时，” 引用计数 “算法就会导致问题；
5. 解除变量的引用不仅有助于消除循环引用现象，而且对垃圾收集也有好处。为了确保有效的回收内存，应该及时解除不再使用的全局对象、全局对象属性以及循环引用变量的引用。

**代码回收规则如下：**

　　　　**1.全局变量不会被回收。**

　　　　**2.局部变量会被回收，也就是函数一旦运行完以后，函数内部的东西都会被销毁。**

　　　　**3.只要被另外一个作用域所引用就不会被回收**

#### 4. 闭包是什么？用let怎么实现闭包？有什么优点和缺点？

闭包是指有权访问另一个函数作用域中的变量的函数。

一个闭包就是**一个没有释放资源的栈区**，栈区内的变量处于激活状态。

闭包：当外部函数返回之后，内部函数可以访问外部函数的属性或者方法。（站友提供的说法）

在ES6中let实际是为js新增了块级作用域。

let声明的变量可以绑定在作用域中。

**优点**：① 能够读取函数内部的变量；②让这些变量一直存在于内存中，不会在调用结束后被垃圾回收机制回收；

**缺点**：由于闭包会使用函数中的变量存在在内存中，内存消耗很大，所以不能滥用闭包；解决的办法是**退出函数之前，将不使用的局部变量删除**；

#### 5. 怎么调程序中出现的代码？

```
alert('方法一')
console.log('方法二') 
Chrome中的开发者工具：断点设置、调试功能
```

#### 6.this的指向问题？

this的最终指向的是那个**调用它的对象**。

改变this指向的方法：

1. 使用**箭头函数**；

> 箭头函数中的this指向**定义时**当前周围的作用域；

1. 在函数内部使用`_this=this;`
2. 使用**apply、call、bind**

> `call`是立即执行传递this的；`bind`不是立即执行的，返回的是函数的副本；

1. new**实例化一个对象**；

在非严格模式下，如果如果函数没有用作构造函数，而是仅仅作为普通函数使用的话，那么函数中的this是指向window的。在严格模式下，this的值就是undefined。

#### 7.js的执行机制：Event loop

![img](https://codingwithalice.github.io/img/assets_2019/%E6%89%A7%E8%A1%8C%E6%9C%BA%E5%88%B6.png)

- 同步和异步任务**分别进入不同的执行”场所”**，同步的进入主线程，异步的进入Event Table并注册函数。
- 当指定的事情完成时，Event Table会将这个函数移入Event Queue。
- 主线程内的任务执行完毕为空，会去Event Queue读取对应的函数，进入主线程执行。
- 上述过程会不断重复，也就是常说的Event Loop(事件循环)。

 `setTimeout`这个函数，是经过指定时间后，**把要执行的任务加入到Event Queue中**，又因为是单线程任务要一个一个执行，如果前面的任务需要的时间太久，那么只能等着，导致真正的延迟时间远远大于设置的时间长度。

 `setInterval`会每隔**指定的时间将注册的函数置入Event Queue**，如果前面的任务耗时太久，那么同样需要等待。唯一需要注意的一点是，对于`setInterval(fn,ms)`来说，我们已经知道不是每过`ms`秒会执行一次`fn`，而是每过`ms`秒，会有`fn`进入Event Queue。一旦**setInterval的回调函数fn执行时间超过了延迟时间ms，那么就完全看不出来有时间间隔了**。

除了广义的同步任务和异步任务，我们对任务有更精细的定义：

- macro-task(宏任务)：包括整体代码script，setTimeout，setInterval
- micro-task(微任务)：Promise，process.nextTick

不同类型的任务会进入对应的Event Queue，比如`setTimeout`和`setInterval`会进入相同的Event Queue。

![img](https://codingwithalice.github.io/img/assets_2019/%E5%AE%8F%E4%BB%BB%E5%8A%A1.png)

进入整体代码(宏任务)后，开始第一次循环。接着执行所有的微任务。然后再次从宏任务开始，找到其中一个任务队列执行完毕，再执行所有的微任务。

#### 8.给DOM元素绑定事件有哪几种方法？

1.使用内联；2.使用`.onclick`的方式；3.使用事件监听`addEventListener`的方式；(IE使用attachEvent)

**1、2两种方式都是存在一个弊端的，就是一个元素只能添加一个事件。**

```
<!--1.内联-->
<input type="button" value="btn" onclick="alert('内联');">
```

 这种方式就是在一个元素上面直接绑定了一个点击`onclick`事件。同时，这个事件的优先级是最高的。

```
<!--2. .onclick的方式-->
<input type="button" value="btn">

<script>
	var btn = document.getElementsBytagname("input")[0];
	btn.onclick = function(){
		alert('.onclick')
	}
</script>
```

使用这种形式也是可以给一个DOM元素添加上一个事件。

**3.给一个元素（DOM对象）添加两个甚至是多个事件**

```
<!--3.事件监听addEventListener-->
<input type="button" value="按钮">

<script>
	var btn = document.getElementsBytagname("input")[0];
	btn.addEventListener("click", function(){
		alert(1)
	})
	btn.addEventListener("click", function(){
		alert(2)
	})
</script>
```

使用`addEventListener`的方式还可以拥有第三个参数：

1. 事件类型，**不需要**添加上`on`
2. 事件函数
3. 是否捕获（布尔值），默认是`false`，即不捕获，那就是冒泡。

```
attachEvent`绑定的事件，如果需要注销，应该使用`detachEvent
```

#### 9.三大事件冒泡、捕获是怎么执行的？

**先捕获再冒泡**

事件冒泡的概念下在p元素上发生click事件的顺序应该是**p -> div -> body -> html -> document**；

事件捕获的概念下在p元素上发生click事件的顺序应该是**document -> html -> body -> div -> p**；

接下来是摘自《红宝书》的总结：

**事件流**描述的是从页面中接收事件的顺序。P348

IE的事件流叫做**事件冒泡**：就是指事件开始时由最具体的元素（文档中嵌套层次最深的的那个节点）接收，然后逐级向上传播到较为不具体的节点（文档）。

div–>body–>html–>document

**事件捕获**：不太具体的节点应该更早接收到事件，而最具体的节点应该最后接收到事件。（用意在于在事件到达预定目标之前捕获它）

document–>html–>body–>div

#### 10.js处理异步的几种方式

**一、回调函数（callback）**

**概念**：回调是一个函数被作为一个参数传递到另一个函数里，在那个函数**执行完后再执行**。

**优点**：回调函数是异步编程最基本的方法，简单、容易理解和部署

**缺点**：不利于代码的阅读和维护，各个部分之间高度耦合，流程会很混乱，而且每个任务只能指定一个回调函数。

**注意 区分**：回调函数和异步 **回调并不一定就是异步。他们自己并没有直接关系。**

**二、事件监听**

采用事件驱动模式。任务的执行不取决代码的顺序，而**取决于某一个事件是否发生**。

**监听函数有：on，bind，listen，addEventListener，observe**

```
//on
f1.on('done',f2);
//或者
function f1(){
    settimeout(function(){
       //...f1的任务代码
       f1.trigger('done');  //执行完成后，立即触发done事件，从而开始执行f2.
    },1000);
}
```

**优点**：容易理解，可以绑定多个事件，每一个事件**可以指定多个回调函数**，而且可以**去耦合，有利于实现模块化。**

**缺点**：整个程序都要变成事件驱动型，运行流程会变得不清晰。

```
element.onclick=function(){
   //处理函数
}
```

**优点**：写法兼容到主流浏览器

**缺点**：当同一个element元素绑定多个事件时，只有最后一个事件会被添加，相当于**一次只能添加一个事件**；

```
//IE:attachEvent;三个方法执行顺序：3-2-1；
elment.attachEvent("onclick",handler1);
elment.attachEvent("onclick",handler2);
elment.attachEvent("onclick",handler3);
//标准addEventListener;执行顺序：1-2-3
elment.addEvenListener("click",handler1,false);
elment.addEvenListener("click",handler2,false);
elment.addEvenListener("click",handler3,false);
```

**注意**：该方法的第三个参数是冒泡获取，是一个布尔值：当为false时表示由里向外（冒泡），true表示由外向里（捕获）。

**三、发布/订阅（又称观察者模式）**

```
//jQuery的一个插件 Ben Alman的Tiny Pub/Sub
jQuery.subscribe("done", f2);//f2向"信号中心"jQuery订阅"done"信号。
jQuery.unsubscribe("done", f2);//取消订阅（unsubscribe）
//或者
function f1(){
　　setTimeout(function () {
　　　　// ...f1的任务代码
　　　　jQuery.publish("done");//f1执行完成后，向"信号中心"jQuery发布"done"信号，从而引发f2的执行
　　}, 1000);
}
```

**四、promise对象（promise 模式）**

**promise是一种模式，promise可以帮忙管理异步方式返回的代码。**将代码进行封装并添加一个类似于事件处理的管理层。我们可以使用promise来注册代码，这些代码会在在promise**成功或者失败后运行**。

我们可以注册任意数量的函数再成功或者失败后运行，也可以在任何时候注册事件处理程序。

promise有两种状态：1、等待（pending）；2、完成（settled）。promise会一直处于等待状态，直到它所包装的异步调用返回/超时/结束。这时候promise状态变成完成。完成状态分成两类：解决（resolved）；拒绝（rejected）。

resolve()函数告诉promise用户promise已解决；reject()函数告诉promise用户promise未能顺利完成。注意then和catch用法，可以将他们想象成onsucess和onfailure事件的处理程序。

```
f1().then(f2).then(f3);
f1().then(f2).fail(f3);
```

**优点**：回调函数写成了**链式写法**，程序的流程可以看得很清楚，而且有一整套的配套方法，可以实现很多强大的功能。**如果一个任务已经完成，再添加回调函数，该回调函数会立即执行**。

**缺点：**编写和理解都相对比较难。

**五、优雅的async/await**

**async** 函数书写的方式跟我们普通的函数书写方式一样，只不过是前面多了一个 `async` 关键字，并且函数返回的是一个 **Promise** 对象，所接收的值就是函数 **return** 的值。

在 **async** 函数内部可以使用 **await** 命令，表示等待一个异步函数的返回。await 后面跟着的是一个 Promise 对象，如果不是的话，系统会调用 `Promise.resolve()` 方法，将其转为一个 resolve 的 **Promise** 的对象。

```
let bar = async function(){  
	try{    
        await Promise.reject('error')
    }catch(e){    
        console.log(e)
    }
}
```

#### 11.JS设置CSS样式的几种方式

 **1. 直接设置style的属性** 某些情况用这个设置 !important值无效

```
element.style.height = '100px';
/*		如果属性有'-'号，就写成驼峰的形式（如textAlign）  
如果想保留 - 号，就中括号的形式  element.style['text-align'] = '100px';*/
```

 **2. 直接设置属性**（只能用于某些属性，相关样式会自动识别）

```
element.setAttribute('height', 100);
element.setAttribute('height', '100px');
```

 **3. 设置style的属性**

```
element.setAttribute('style', 'height: 100px !important');
```

 **4. 使用setProperty** 如果要设置!important，推荐用这种方法设置第三个参数

```
element.style.setProperty('height', '300px', 'important');
```

 **5. 改变class** 比如JQ的更改class相关方法

```
element.className = 'blue';
element.className += 'blue fb';
/*因JS获取不到css的伪元素，所以可以通过改变伪元素父级的class来动态更改伪元素的样式*/
```

 **6. 设置cssText**

```
element.style.cssText = 'height: 100px !important';
element.style.cssText += 'height: 100px !important';
```

 **7. 创建引入新的css样式文件**

```
	function addNewStyle(newStyle) {
            var styleElement = document.getElementById('styles_js');
            if (!styleElement) {
                styleElement = document.createElement('style');
                styleElement.type = 'text/css';
                styleElement.id = 'styles_js';
                document.getElementsByTagName('head')[0].appendChild(styleElement);
            }  
            styleElement.appendChild(document.createTextNode(newStyle));
     }
	addNewStyle('.box {height: 100px !important;}');
```

 **8. 使用addRule、insertRule**

```
		// 在原有样式操作
        document.styleSheets[0].addRule('.box', 'height: 100px');
        document.styleSheets[0].insertRule('.box {height: 100px}', 0);
 
        // 或者插入新样式时操作
        var styleEl = document.createElement('style'),
            styleSheet = styleEl.sheet;
 
        styleSheet.addRule('.box', 'height: 100px');
        styleSheet.insertRule('.box {height: 100px}', 0);
 
        document.head.appendChild(styleEl);  
```

#### 12.点击网页任意空白区域隐藏div

```
$('.phone_cell').on('click',function(event){
    //取消事件冒泡  
    event.stopPropagation();
    $('.ulfix').slideToggle();
});
//点击空白处隐藏弹出层，下面为消失效果
$(window).click(function(){
    if ($('.ulfix').css('display')!='none') {
        $('.ulfix').slideToggle();
    }    
});
```

需要注意的是如果单层里面本身还有点击事件，如果点击自身也会出现消失的情况 ，解决办法给点击事件增加

#### 13.js的基本数据类型及其判断方法

**值类型(6个基本类型)**：字符串（String）、数字(Number)、布尔(Boolean)、空（Null）、未定义（Undefined）、Symbol（ES6引入，表示独一无二的值）。

**引用数据类型**（又称Object类型）：对象(Object)、数组(Array)、函数(Function)、Date 类型、RegExp 类型（正则）。

注意：基本数据类型值不可变，基本类型的比较是值的比较；引用类型值可变，引用类型的比较是引用的比较；

**检测类型常用的有typeof和instanceof：**

①typeof：经常用来检测一个变量是不是最基本的数据类型

```
var a;typeof a;    	// undefined，声明未赋值
a = true;typeof a;    // boolean
a = 666;typeof a;    // number 
a = "hello";typeof a;    // string
a = Symbol();typeof a;    // symbol
a = [];typeof a;    // object
a = {};typeof a;    // object
a = /aaa/g;typeof a;    // object

a = null;typeof a;    // object，注意null判断出来的类型是object
a = function(){};typeof a;    // function，注意function判断出来的类型是function而不是object
```

②instanceof：判断一个引用类型的变量具体是不是某种类型的对象

```
({}) instanceof Object              // true
([]) instanceof Array               // true
(/aa/g) instanceof RegExp           // true
(function(){}) instanceof Function  // true
```

#### 14.怎么判断数组类型？5种方法

typeof运算符，constructor法，instanceof运算符，Object.prototype.toString方法以及Array.isArray法

**①typeof**：javascript原生提供的判断数据类型的运算符，它会返回一个表示参数的数据类型的字符串；但是数组，对象，正则，null经过这个判断得到的都是object，**并不能识别出数组**

```
const s = [];
console.log(typeof(s))//object
```

**②instanceof运算符**：判断某个构造函数的prototype属性所指向的對象是否存在于另外一个要检测对象的原型链上。如果这个Object的**原型链上能够找到Array构造函数**的话，那么这个Object应该及就是一个数组，如果这个Object的原型链上只能找到Object构造函数的话，那么它就不是一个数组。

```
({}) instanceof Object              // true
([]) instanceof Array               // true
```

**③constructor**：实例化的数组拥有一个constructor属性，这个属性指向生成这个数组的方法。但是constructor属性可以改写，**判断的结果不靠谱**。

```
const a = [];console.log(a.constructor);//function Array(){ [native code] }
console.log(a.constructor==Array);//true
const o = {};console.log(o.constructor);//function Object(){ [native code] }
const r = /^[0-9]$/;console.log(r.constructor);//function RegExp() { [native code] }
const n = null;console.log(n.constructor);//报错
```

**④Object.prototype.toString**：每一个继承自Object的对象都拥有toString的方法，toString方法将会返回”[object *type*]”，其中的***type\*代表的是对象的类型**，根据type的值，我们就可以判断这个疑似数组的对象到底是不是数组了。**但是对象的toString方法也可以重写，可能会判断出错**。

注意：不能直接使用数组的。toString方法，会返回字符串，如下：

```
const a = ['Hello','world'];a.toString();//"Hello,world"
const b = {0:'Hello',1:'world'};b.toString();//"[object Object]"
const c = 'Hello world';c.toString();//"Hello,world"
```

所以要判断除了对象之外的数据的数据类型，我们需要“借用”对象的toString方法，使用**call或者apply方法来改变toString方法的执行上下文**：

```
const a = ['Hello','world'];Object.prototype.toString.call(a);//"[object Array]"
						    Object.prototype.toString.apply(a);//"[object Array]"
const c = 'Hello world';Object.prototype.toString.call(c);//"[object String]"
						Object.prototype.toString.apply(c);//"[object String]"
```

**⑤isArray方法**：最靠谱的判断数组的方法

```
const a = [];Array.isArray(a);//true
const b = {};Array.isArray(b);//false
```

经过验证，即使重写了Object.prototype.toString方法、修改了constructor对象是不影响判断的结果的。

#### 16.深拷贝和浅拷贝的区别？怎么实现深拷贝？

| –      | 是否指向原对象 | 第一层数据为基本数据类型     | 原数据中包含引用数据类型     |
| :----- | :------------- | :--------------------------- | :--------------------------- |
| 赋值   | 是             | 改变会使原数据一同改变       | 改变会使原数据一同改变       |
| 浅拷贝 | 否             | 改变**不**会使原数据一同改变 | 改变会使原数据一同改变       |
| 深拷贝 | 否             | 改变**不**会使原数据一同改变 | 改变**不**会使原数据一同改变 |

**赋值**是赋的是该对象的在栈中的地址，而不是堆中的数据，也就是两个对象指向的是同一个存储空间，是联动的；

**浅拷贝**只复制一层对象的属性，如果属性是基本类型，拷贝的就是基本类型的值；如果属性是内存地址（引用类型），拷贝的就是内存地址 ，并不包括对象里面的为引用类型的数据；

**浅拷贝的实现**：

1.Object.assign()：把任意多个的源对象自身的可枚举属性拷贝给目标对象，然后返回目标对象，拷贝的是对象的属性的引用，而不是对象本身。

```
var obj = { a: {a: "copy", b: 1} };
var newlObj = Object.assign({}, obj);//-----------
initalObj.a.a = "swallow";
console.log(obj.a.a); //swallow
```

2.Array.prototype.concat()：修改新对象会改到原对象

```
let arr = [1, 2, {    username: 'copy'    }];
let arr2=arr.concat();//----------------    
arr2[2].username = 'swallow';
console.log(arr);
```

3.Array.prototype.slice()：同样修改新对象会改到原对象

```
let arr = [1, 2, {    username: 'copy'    }];
let arr2=arr.slice();//----------------    
arr2[2].username = 'swallow';
console.log(arr);
```

注：Array的slice和concat方法不修改原数组，只会返回一个浅复制了原数组中的元素的一个新数组。

**深拷贝**是对对象以及对象的所有子对象进行拷贝。

**深拷贝的实现**：

1.JSON.parse(JSON.stringify())：用JSON.stringify将对象转成JSON字符串，再用JSON.parse()把字符串解析成对象，一去一来，**新的对象产生了，而且对象会开辟新的栈**，可以**实现数组或对象深拷贝**，但**不能处理函数**。

因为JSON.stringify() 方法是将一个JavaScript值(对象或者数组)转换为一个 JSON字符串，不能接受函数

```
let arr = [1, 3, {    username: ' copy'}];
let arr2 = JSON.parse(JSON.stringify(arr));
arr2[2].username = 'shen'; 
console.log(arr, arr4)
```

2.递归：递归方法实现深度克隆原理：**遍历对象、数组直到里边都是基本数据类型，然后再去复制，就是深度拷贝**。

```
    //定义检测数据类型的功能函数
    function checkedType(target) {
      return Object.prototype.toString.call(target).slice(8, -1)
    }
    //实现深度克隆---对象/数组
    function clone(target) {
      //判断拷贝的数据类型
      //初始化变量result 成为最终克隆的数据
      let result, targetType = checkedType(target)
      if (targetType === 'Object') {
        result = {}
      } else if (targetType === 'Array') {
        result = []
      } else {
        return target
      }
      //遍历目标数据
      for (let i in target) {
        //获取遍历数据结构的每一项值。
        let value = target[i]
        //判断目标结构里的每一值是否存在对象/数组
        if (checkedType(value) === 'Object' ||
          checkedType(value) === 'Array') { //对象/数组里嵌套了对象/数组
          //继续遍历获取到value值
          result[i] = clone(value)
        } else { //获取到value值是基本的数据类型或者是函数。
          result[i] = value;
        }
      }
      return result
    }
    // 内部方法：用户合并一个或多个对象到第一个对象
    // 参数：
    // target 目标对象  对象都合并到target里
    // source 合并对象
    // deep 是否执行深度合并
    function extend(target, source, deep) {
        for (key in source)
            if (deep && (isPlainObject(source[key]) || isArray(source[key]))) {
// source[key]是对象，而target[key]不是对象，则target[key]={}初始化一下，否则递归会出错的
                if (isPlainObject(source[key]) && !isPlainObject(target[key]))
                    target[key] = {}

// source[key] 是数组，而 target[key]不是数组，则 target[key] = []初始化一下，否则递归会出错的
                if (isArray(source[key]) && !isArray(target[key]))
                    target[key] = []
                // 执行递归
                extend(target[key], source[key], deep)
            }
            // 不满足以上条件，说明 source[key] 是一般的值类型，直接赋值给 target 就是了
            else if (source[key] !== undefined) target[key] = source[key]
    }

    // Copy all but undefined properties from one or more
    // objects to the `target` object.
    $.extend = function(target){
        var deep, args = slice.call(arguments, 1);

        //第一个参数为boolean值时，表示是否深度合并
        if (typeof target == 'boolean') {
            deep = target;
            //target取第二个参数
            target = args.shift()
        }
        // 遍历后面的参数，都合并到target上
        args.forEach(function(arg){ extend(target, arg, deep) })
        return target
    }
```

#### 17.数组常用的遍历方法有哪几种？（for…in一般用于对象）

- 1.普通for循环

- 性能：使用频率最高，性能不弱，但仍有优化空间

  ```
  for(j = 0; j < arr.length; j++) {}
  ```

- 2.优化版for循环

- 性能：使用临时变量，将长度缓存起来，避免重复获取数组长度，当数组较大时优化效果才会比较明显。

  基本上是所有循环遍历方法中**性能最高**的一种。

  ```
  for(j = 0,len=arr.length; j < len; j++) {}
  ```

- 3.foreach循环，没有返回值，纯粹用来遍历数组

- 性能：数组自带的foreach循环，性能比普通for循环弱

  ```
  let numbers = [1, 2, 3, 4];    
  numbers.forEach((item, index, array)=>{        
    // 执行某些操作    
  })
  ```

- 4.for…in循环

- 性能：

  效率最低

  ，不推荐用于数组遍历，一般用于对象循环

  ```
  for(j in arr) {} 
  ```

- 5.for…of循环

- 性能：性能好于for…in，但仍**低于普通for循环**

  不仅可以遍历数组，还可以遍历Map、Set这两种ES6新推出的数据结构。

```
let numbers = [1, 2, 3, 4];
for(let item of numbers){    
    console.log(item);
}
//输出
// 1
// 2
// 3
// 4
```

- map遍历

- 注意： map() 不会对空数组进行检测；map() 不会改变原始数组。

  对数组的每一项运行给定函数，返回每次函数调用的返回值组成的数组。

```
let numbers = [1, 2, 3, 4];    
let mapResult = numbers.map((item, index, array)=>{        
    return item * 2;    
})    
console.log(mapResult); // 输出 [2, 4, 6, 8]
```

性能：比较优雅，**低于普通for循环**，还比不上foreach

- 大致比较如下：for循环 > forEach > for…of > for…in > map

还有几个用的比较少的es5的循环方法：

**every( )**：对数组中的每一项运行给定函数，如果该函数对每一项都返回true，则every( )返回truelet

```
 numbers = [1, 2, 3, 4];    
let everyResult = numbers.every((item, index, array)=>{        
    return item > 1;    
})    
console.log(everyResult);  // 输出 false
```

**filter( )**：对数组中的每一项运行给定函数，然后返回该函数会返回true的项。

```
let numbers = [1, 2, 3, 4];    
let filterResult = numbers.filter((item, index, array)=>{        
    return item > 1;    
})    
console.log(filterResult);  // 输出 [2, 3, 4]
```

| **some( )**：对数组的每一项运行给定函数，如果该函数对任一项返回true，则some( )就返回true。some和every就像 |      | 和 &&，some是只要有一项满足，就返回true。 |
| ------------------------------------------------------------ | ---- | ----------------------------------------- |
|                                                              |      |                                           |

```
let numbers = [1, 2, 3, 4];    
let someResult = numbers.some((item, index, array)=>{        
    return item > 3;    
})    
console.log(someResult);  // 输出 true
```

注意：ES5的这几个迭代方法，如果是只对item（当前遍历的数组项）进行操作，是**不会改变原数组**的，但是也可以通过给定函数中接收的index参数来改变原数组使用选择的时候，以现在的硬件水平，这里的差异其实可以忽略，**考虑语义和功能需求来选择**：

如果你需要**将数组按照给定规则转换**并**返回该结果数组**，就使用map。

如果你需要进行**简单的遍历**，用 forEach 或者 for of，但是 forEach 不能通过return和break语句来终止循环，所以

如果需要**中途终止循环**，就使用 for…of或者 for循环。

如果是在遍历数组的同时，需要**改变原数组**中的对应项，就用for循环。

for…in会把数组所拥有可枚举的属性都遍历一次，所以可能会有意想不到的结果，不推荐用来遍历数组。

另外的三个，every( )、filter( )、some( )按功能需要来使用即可。

#### 18.JS获取url参数

```
function getQueryVariable(variable)
{
       var query = window.location.search.substring(1);
       var vars = query.split("&");
       for (var i=0;i<vars.length;i++) {
               var pair = vars[i].split("=");
               if(pair[0] == variable){return pair[1];}
       }
       return(false);
}
```

#### 19.在js的浏览器对象模型中，window对象的（status）属性是用来指定浏览器状态栏里面的临时消息

status：状态栏信息属性

screen：屏幕对象（也叫显示屏对象）

history：网页历史对象

document：文本对象

#### 20.隐式转换（三种）掘金有篇博客:你所忽略的js隐式转换

`+`运算符即可数字相加，也可以字符串相加。所以转换时很麻烦。

`== `不同于===，故也存在隐式转换。

`- * /` 这些运算符只会针对number类型，故转换的结果只能是转换成number类型。

隐式转换中主要涉及到三种转换：

 1、**将值转为原始值**，ToPrimitive(input, PreferredType?)。

valueOf(),toString()

PreferredType没有设置时，Date类型的对象，PreferredType默认设置为String，其他类型对象PreferredType默认设置为Number。

 2、**将值转为数字**，ToNumber()。.

| 参数      | 结果                                                         |
| :-------- | :----------------------------------------------------------- |
| undefined | NaN                                                          |
| null      | +0                                                           |
| 布尔值    | true转换1，false转换为+0                                     |
| 数字      | 无须转换                                                     |
| 字符串    | 有字符串解析为数字，例如：‘324’转换为324，‘qwer’转换为NaN    |
| 对象(obj) | 先进行 ToPrimitive(obj, Number)转换得到原始值，在进行ToNumber转换为数字 |

 3、**将值转为字符串**，ToString()。

| 参数      | 结果                                                         |
| :-------- | :----------------------------------------------------------- |
| undefined | ‘undefined’                                                  |
| null      | ‘null’                                                       |
| 布尔值    | 转换为’true’ 或 ‘false’                                      |
| 数字      | 数字转换字符串，比如：1.765转为’1.765’                       |
| 字符串    | 无须转换                                                     |
| 对象(obj) | 先进行 ToPrimitive(obj, String)转换得到原始值，在进行ToString转换为字符串 |

举例

```
({} + {}) = ?
两个对象的值进行+运算符，肯定要先进行隐式转换为原始类型才能进行计算。
1、进行ToPrimitive转换，由于没有指定PreferredType类型，{}会使默认值为Number，进行ToPrimitive(input, Number)运算。
2、所以会执行valueOf方法，({}).valueOf(),返回的还是{}对象，不是原始值。
3、继续执行toString方法，({}).toString(),返回"[object Object]"，是原始值。
故得到最终的结果，"[object Object]" + "[object Object]" = "[object Object][object Object]"
```

在`==`进行转换时，

1.类型相同时，没有类型转换，主要**注意NaN不与任何值相等，包括它自己**，即NaN !== NaN

2.类型不相同时，

**x,y 为null、undefined两者中一个 // 返回true**

**x、y为Number和String类型时，则转换为Number类型比较**。

有Boolean类型时，**Boolean转化为Number类型比较**。

一个Object类型，一个String或Number类型，将Object类型进行原始转换后，按上面流程进行原始值比较。

#### 21.使用setTimeout模拟setInterval

```
var i=0;
setInterval(function(){
	i=i++;
	console.log(i)
},1000)
//使用setTimeout也可以产生setInterval的效果
var i=0;
function intv(){
    setTimeout(function(){
        consolr.log(i++);
        intv()
    },1000)
}
intv()
```

但是setInterval和intv()还是有些差别

```
/intv()函数表示在函数执行完成之后的一秒再执行下一个函数
函数A(执行时间)-->(1s)-->函数B(执行时间)-->(1S)-->函数C(执行时间)-->(1S);
/setInterval表示函数执行的间隔为1秒钟,可以这样认为
(函数A(执行时间)+(间隔时间))=(1S)-->(函数B(执行时间)+(间隔时间))=(1S)-->(函数C(执行时间)+(间隔时间))=(1S)
```

#### 22.计算数字各位相加之和

```
// 初始化 sum（和）为 0
var a = 283, sum = 0;            
for(var i = 0; i < a.toString().length; i++) {
    alert(a.toString()[i]);    
    // 每一位相加
    // 第一次 0 + 2，第二次 2 + 8，第三次 10 + 3
    sum += parseInt(a.toString()[i]);
}            
alert(sum);//13
```

#### 23.数据结构中”遍历”是什么意思?

所谓遍历，是指沿着某条搜索路线，**依次对树中每个结点均做**一次且仅做一次访问。

#### 24.在js中，两个整数进行除（/）运算，结果也为整数吗？不是，是小数

在js中计算5/2，不会像在java中得到2，结果会是2.5，那如何得到整数2呢，整合下搜索结果，总共有以下几种方法：

1. parseInt(5/2)

2. Math.floor(5/2)

3. | 5/2  | 0    |
   | ---- | ---- |
   |      |      |

| 第三种特别说明下，’ | ‘是位运算符，js中位运算之前会转为整数，与0位运算结果还是本身，所以也能达到取整数的目的。 |
| ------------------- | ------------------------------------------------------------ |
|                     |                                                              |

#### 24.form标签对之间，可以出现p、ul等非表单域元素吗？可以

#### 25.bind、apply、call三者区别？用apply实现bind

![1571448536088](https://codingwithalice.github.io/img/assets_2019/1571448536088.png)

#### 26.画一下原型链，`prototype`和`__proto__`有什么区别

![1572010026168](https://codingwithalice.github.io/img/assets_2019/1572010026168.png)

`prototype`和`__proto__`有什么区别：

![1575295251658](https://codingwithalice.github.io/img/assets_2019/1575295251658.png)

`__proto__`指向的是这个对象的构造函数的prototype；A函数的构造函数是Object

![1575295456546](https://codingwithalice.github.io/img/assets_2019/1575295456546.png)

#### 27.删除表格的第一行有哪些方法

方法一：removeChild

```
var tds = table.getElementsByTagName("td");
var tr = tds[0].parentNode;
tr.parentNode.removeChild(tr);
```

方法二：deleteRow

```
var trs = document.getElementsByTagName("tr");
var table = document.getElementById("table");
table.deleteRow(0);//删除第一行
```

方法三：jQuery：remove、detach、empty

```
<script src="https://cdn.bootcss.com/jquery/3.3.1/jquery.min.js"></script>
function delRow(row_id){ 
  $(row_id).remove(); //方法1，删移除元素及它的数据和事件
  $(row_id).detach(); //方法2，移除被选元素，包括所有的文本和子节点。然后它会保留数据和事件。
  $(del).empty(); //方法3，从被选元素移除内容
} 
```

方法四：样式

```
var tds = table.getElementsByTagName("td");
var tr = tds[0].parentNode;
tr.style.display='none';//方法1，不保留原有位置
tr.style.opacity=0;//方法2，保留原有位置
tr.style.visibility='hidden';//方法3，保留原有位置
```

#### 28.jQuery有哪些方法可以选择一个表格中的第一行

```
$("#id") //id=“id”的元素
$(".class") //class=“class”的元素
$("p") //所有<p>元素
$(".intro.demo") //所有 class="intro" 且 class="demo" 的元素
$("p:first") //第一个<p>元素
$("p:last")	//最后一个<p>元素
$("tr:even") //所有偶数<tr>元素
$("tr:odd")	//所有奇数<tr>元素
$("ul li:eq(3)") //列表中的第四个元素（index从0开始）
$("ul li:gt(3)") //列出index大于3的元素
$("ul li:lt(3)") //列出index小于3的元素
$("[href]")	//所有带有href属性的元素
$(":input")	//所有<input>元素
$(":checked") //所有被选中的input元素
```

#### 29.扁平化一个嵌套的数组

```
let arrays = [1, [2, [3, [4, 5]]], 6];
```

需求：多维数组=>一维数组

第一种方法：直接调用arr的flat方法

```
arr = arrays.flat(Infinity);//[1, 2, 3, 4, 5, 6]
```

第二种方法：正则表达式

```
let str = JSON.stringify(arrays);
arr = str.replace(/(\]|\[)/g, '').split(',');//["1", "2", "3", "4", "5", "6"]
```

第三种：正则表达式

```
str = str.replace(/(\[|\])/g, '');
str = '[' + str + ']';
ary = JSON.parse(str);//[1, 2, 3, 4, 5, 6]
```

第四种：递归

```
let result = [];
function fn(array) {
    for (let i = 0; i < array.length; i++) {
        let item = array[i];
        if (Array.isArray(array[i])) {
            fn(item);
        } else {
            result.push(item);
        }
    }
}
fn(arrays)
```

第五种：reduce

```
const flatten = (arr) => {
  return arr.reduce((prev, next) => {
    return prev.concat(Object.prototype.toString.call(next) === '[object Array]' ? flatten(next): next)
  }, [])
}
```

第六种：…扩展运算符

【注意】：扩展运算符（…）内部使用for…of循环

```
while (arrays.some(Array.isArray)) {
	arrays = [].concat(...arrays);
}//[1, 2, 3, 4, 5, 6]
```

------



# html相关 面试问题

#### 1. h5新标签有哪些？为什么要加强语义化？

新标签：

**文档类型设定**：`<!doctype html>`；

**字符设定**：`<meta charset="utf-8">`；

**常用新标签**：

 `header`，一般作为网页的**头部**使用，可以多个；

 `footer`，底部，**不一定是文档最底部**，可以多个；

 `aside`，**侧边**栏；

 `nav`，**导航**栏；

 `article`，独立内容区域，与session类似，**用于文章blog、帖子、短文或者回复、评论**等；

 `section`，代表某一个区域/分区/页面/文档的**一部分区域**，有独立的内容，但结构相近，就可以用section，范围比div大，语义比div更强，可以包含header、`h1-h6`……凸显语义的标签；

 `datalist `，**标签定义选项列表**，请与 input 元素配合使用该元素；

```
<input type="text" value="输入" list="TFboys"/> <!--  input里面用list -->
<datalist id="TFboys">   <!-- datalist里面用id -->  
        <option>易烊千玺</option>
        <option>王俊凯</option>
        <option>王源</option>
</datalist>
```

 `fieldset`，可**将表单内的相关元素分组**，打包legend（为`fieldset`元素定义标题）使用；

```
	<fieldset>
	<legend>用户登录</legend>
    	用户名: <input type="text"><br />
		密　码: <input type="password">
    </fieldset>
```

 `address`，**标签定义文档或文章的作者/拥有者的联系信息**，字体样式默认倾斜； `time`，时间标签，主要用于搜索引擎和其它一些内容引擎特殊的解析和展示； `hgroup`，专门用来包含标题**h标签的分组**；

 `detail`，*细节、详情* ，open属性：默认展开，summary相当于详情的标题；

 **新增了许多input type属性**：`email`、`tel`、`url`、`number`、`search搜索框，加强语义`、`range自由拖动滑块`、`time`、`date日期`、`datetime时间`、`month`、`week`

 **新增了许多input的属性**：`placeholder占位符，默认文字`、`autofocus页面加载时自动获得焦点`、`multiple多文件上传`、`autocomplete`、`required必填项`、`accesskey规定激活元素的快捷键`

 **多媒体标签**：`embed定义嵌入的内容`、`audio播放音频`、`video播放视频`；

 `src导入`，`autoplay自动播放`、`controls是否默认显示播放件`、`loop循环播放`

 ……

 原因：1.默认样式不一样 ；2.有SEO优化作用；

#### 2.行内元素、块元素有哪些？它们有什么不同？

行内元素：b、span、a、u、em、i、img、input、select、label、textarea、button

块级元素：div、h、ol、ul、dl、li、table、td、th、tr、dd、dt、p、caption

空元素：area、meta、link

- 行内元素的特点：

  1、行内元素**只能容纳文本或者其他行内元素**。

  2、**宽度只与内容有关**。

  3、和其他元素都**在一行上**。

  4、高，行高及外边距和内边距**左右可改变**。

- 块级元素的特点：

  1、高度，行高以及外边距和内边距**都可控制**。

  2、总是在新行上开始，**占据一整行**。

  3、它可以**容纳内联元素和其他块元素**。

  4、**宽度**始终是与浏览器宽度一样，**与内容无关**。

- 区别：

  1、**行内元素**会在**一条直线上分列**，都是统一行的，程度偏向分列。

   **块级元素各盘踞一行**，垂直偏向分列；块级元素重新行开端停止接着一个断行。

  2、**行内元素**不可以包括块级元素，只能包容文本或许其余行内元素。

   **块级元素**能够包括行内元素和块级元素，还能够包容内联元素和其余元素；。

  3、行内元素与块级元素属性的分歧，主要在盒模子属性上。

  **行内元素**设置width无效，height无效（**能够设置line-height**），margin、padding设置上下有效。

- 行内元素内嵌块级元素。高度被子元素撑大，而**宽度和父级一致**（父级是body就是body的宽度）。

- **行内块元素**内嵌块级元素。宽高都会**被子元素撑大**的。

#### 3.html中首行<!doctype>的作用？

 **文档类型声明**，目的是告诉标准通用标记语言解析器要使用什么样的文档类型定义（DTD）来解析文档；声明必须是HTML文档的第一行，位于html标签之前；

#### 4.rem相对于根节点。em相对于父元素

#### 5.一般html网页元素加载完成后，会触发哪个事件？onready比onload先执行

##### Dom文档加载的步骤：

1. 解析html结构；
2. **加载外部**脚本和样式表文件；
3. 解析并执行脚本；
4. dom树构建完成（DOMContentLoaded）；
5. 加载图片等外部文件；
6. 页面加载完毕。

DOM ready：（也叫DOMContentLoaded ），在第4步完成后触发； 图片onload：是在第5步完成后触发； 页面onload：是第6步完成后触发。

由此可见三者执行顺序为：**domready→图片load→页面load。**

执行时间上，**onready比onload先执行**：

 **window.onload**必须等到页面内包括图片的**所有元素加载完毕后才能执行**。

 **$(document).ready()**是**DOM结构绘制完毕后就执行**，不必等到加载完毕。

**onload只执行最后一个**而**onready可以执行多个**：

编写个数不同 window.onload不能同时编写多个，如果有多个window.onload方法，只会执行最后一个。 **$(document).ready()可以同时编写多个，并且都可以按顺序得到执行**。

注：$(document).ready(function(){})可以简写成$(function(){});

#### 6.html是怎么渲染的

1.解析html文件，创建DOM树 自上而下解析，遇到任何样式（link、style）和脚本（script）都会阻塞 　　1）css加载不会阻塞html文件的解析，但会阻塞dom的渲染 　　2）css加载会阻塞后面js语句的执行 　　3）js会阻塞html的解析和渲染 　　4）没有defer和async标签的script会立即加载并执行 　　5）有async标签的js，js的加载执行和html的解析和渲染并行 　　6）有defer标签的js，js的加载和html的解析和渲染并行，但会在html解析完成后执行,在触 发DOMContentLoaded事件前执行 　　7）DOMContentLoaded和onload的区别：DOMContentLoaded在html解析完毕后执行，loload在页面完全加载完成后执行（包括样式和图片） 2.解析css，生成CSSOM，css对象模型 3.dom和css合并，构建渲染树（Render Tree） 4.布局（Layout）和绘制（Paint），重绘（repaint）和重排（reflow/回流） 1）重绘：根据元素的新属性重新绘制，使元素呈现新的外观 　　2）重排：当渲染树中的一部分因为元素的规模尺寸，布局，隐藏等改变而需要重新构建 　　3）重排必定会引发重绘，但重绘不一定会引发重排

#### 7.滚动条

只要网页内容大于视窗，滚动条就会出现。

目标：没有滚动条影响美观，但仍旧可以滚动

**方法1**：在webkit内核的浏览器里可以定义滚动条样式，在CSS初始处定义

```
--Chrome--
body::-webkit-scrollbar{
	display:none;
}
--IE/Edge--
body{
    -ms-overflow-style: none;
}
--Firefox--
html {
    overflow: -moz-hidden-unscrollable; /*注意！若只打 hidden，chrome 的其它 hidden 会出问题*/
    height: 100%;
}

body {
	height: 100%;
	width: calc(100vw + 18px); /*浏览器滚动条的长度大约是 18px*/
	overflow: auto;
}
```

方法2：在div外面再套一个div，内层是有滚动条的，但是我们看不到了

外面的div设置overflow:hidden；

里面的div设置 overflow-y: scroll;overflow-x: hidden;

再设置外层div的width小于内层div的width。

```
<div class="outer">
    <div class="inner">     
    </div>
</div>
.outer{
	overflow:hidden;
    width:200px;
}
.inner{
    overflow-y:scroll;
    overflow-x:hidden;
    width:220px;
}
```





# 盒模型有哪些？有什么区别？

盒模型分为IE盒模型和W3C标准盒模型。

1. **W3C 标准盒模型content-box**：属性width,height只包含内容content，不包含border和padding。
2. **IE 盒模型border-box**：属性width,height包含border和padding，指的是content+padding+border。

**box-sizing**控制，默认值为**content-box，即标准盒模型**；**border-box则用的是IE盒模型**。



# es6相关 面试问题

#### 2.如果使用标记模板字面量，第一个参数的值总是字符串的数组。其余的参数获取的是传递的表达式的值；

#### 3. es6中和原型一样用来继承的class和继承是怎么实现的？

贴上

```
class Point {
  // ...
}
typeof Point // "function"，类的数据类型就是函数
Point === Point.prototype.constructor // true，类本身就指向构造函数
```

使用的时候，也是直接对类使用`new`命令，跟构造函数的用法完全一致，不使用new会报错。

类的所有方法都定义在类的`prototype`属性上面。

```
class Point {
  constructor() {    // ...  }
  toString() {    // ...  }
  toValue() {    // ...  }
}
// 等同于
Point.prototype = {
  constructor() {},
  toString() {},
  toValue() {},
};

//Object.assign方法可以很方便地一次向类添加多个方法
Object.assign(Point.prototype, {
  toString(){},
  toValue(){}
});
```

**类不存在变量提升**（hoist），这一点与 ES5 完全不同。

Class 可以通过`extends`关键字实现继承。

```
class ColorPoint extends Point {}//ColorPoint继承了Point类所有的属性和方法
```

`super`关键字，表示父类的构造函数，用来新建父类的`this`对象。

子类必须在`constructor`方法中调用`super`方法，否则新建实例时会报错，只有调用`super`之后，才可以使用`this`关键字。

**区别：**

ES5 的继承，实质是**先创造子类的实例对象`this`**，然后再将父类的方法**添加到`this`上面**（`Parent.apply(this)`）。

ES6 的继承机制完全不同，实质是**先将父类实例对象的属性和方法，加到`this`上面**（所以必须先调用`super`方法），然后再用子类的构造函数**修改`this`。**

Class 作为构造函数的语法糖，同时有`prototype`属性和`__proto__`属性，因此同时存在两条继承链。

（1）子类的`_proto_`属性，表示构造函数的继承，总是指向父类。

（2）子类`prototype`属性的`_proto_`属性，表示方法的继承，总是指向父类的`prototype`属性。

子类实例的`__proto__`属性的`__proto__`属性，指向父类实例的`__proto__`属性。也就是说，子类的原型的原型，是父类的原型。

`Object.getPrototypeOf`方法判断，一个类是否继承了另一个类。

#### 4. es6中const、let、var之间的区别？

1. var定义的变量，**作用域**是整个封闭函数，是全域的；

   let定义的变量，作用域是在**块级或者字块**中；

2. **变量提升**：不论通过var声明的变量处于当前作用于的第几行，都会提升到**作用域的最顶部**。

   而let声明的变量不会在顶部初始化，凡是在let声明之前使用该变量都会报错（引用错误ReferenceError）；

3. 只要块级作用域内存在`let`，它所声明的变量就会**绑定在这个区域**；

4. **let不允许**在相同作用域内**重复声明**（报错同时使用var和let，两个let）

const用来专门声明一个常量，它跟let一样作用于**块级作用域**，**没有变量提升**，**重复声明会报错**，不同的是**const声明的常量不可改变，声明时必须初始化（赋值）**，const定义的对象可变。

const使用场景很广，包括常量、配置项以及引用的组件、定义的 “大部分” 中间变量等，都应该以cosnt做定义。反之就 let 而言，他的使用场景应该是**相对较少**的，我们只会在 loop(for，while 循环)及少量必须重定义的变量上用到他。

#### 5. 大致讲一下ES6新特性；

① **箭头函数**；

② 增加了对类的**支持class关键字**；继承：`class Programmer extends Animal`

③ 增强了**对象字面量**：可以在对象字面量里面**定义原型**

`__proto__: human, //设置此对象的原型为human,相当于继承human `；

定义方法**可以不用function关键字**

`work() {console.log('working...'); } `；

④ **字符串模板**：反引号 ` 来创建字符串；

⑤ **解构**：[name,age]=[Alice,’male’,’secrect’];//数组解构；

⑥ 参数默认值，不定参数，拓展参数：

 **参数默认值**：在定义函数的时候指定参数的默认值

```
function sayHello2(name='dude'){
	console.log(`Hello ${name}`);
}
```

 **不定参数**：在函数中使用命名参数同时接收不定数量的未命名参数，**三个句点后跟代表所有不定参数的变量名**。

```
function add(...x){
	return x.reduce((m,n)=>m+n);
}
```

 **拓展参数**：允许传递数组或者类数组直接做为函数的参数而不用通过apply。

```
var people=['Wayou','John','Sherlock'];
sayHello(...people);//输出：Hello Wayou,John,Sherlock
```

⑦ `let` 与`const`关键字

⑧ `for of `值遍历：for in 循环用于遍历数组，类数组或对象，for of循环功能相似，不同的是每次循环它**提供的不是序号而是值**。

**for…of** 循环的i代表的是value（**多用于数组**），**for…in** 循环的是key（**多用于对象**）

⑨ iterator, generator：iterator拥有一个next方法；generator是一种特殊的iterator，通过function*来声明的，**yield 关键字**可以暂停函数的执行，随后可以再进进入函数继续执行。

⑩ **模块module**

```
// point.js
module "point" {
    export class Point {
        constructor (x, y) {
            public x = x;
            public y = y;
        } 
    }
}

// myapp.js
module point from "/point.js";	//声明引用的模块
import Point from "point";		//可以看出，尽管声明了引用的模块，还是可以通过指定需要的部分进行导入
var origin = new Point(0, 0);
console.log(origin);
```

① **Map，Set 和 WeakMap，WeakSet**：提供了更加方便的获取属性值的方法，不用像以前一样用hasOwnProperty来检查某个属性是属于原型链上还是当前对象的。同时，在进行属性值添加与获取时有专门的get，set 方法。WeakMap,WeakSet更加安全，作为属性键的对象如果没有别的变量在引用它们，则会被回收释放掉。

② Proxies：**监听对象**身上发生了什么事情，并在这些事情发生后执行一些相应的操作。

③ Symbols：是一种基本类型，不是一个对象。可以用symbol这种值来做为对象的键。

④ Math，Number，String，Object 的新API；

⑤ Promises：**处理异步操作的一种模式**，then()

#### 6.Object.assign浅拷贝

Object.assign方法用来将源对象（source）的所有可枚举属性，复制到目标对象（target）。

Object.assign方法实行的是**浅拷贝**，而不是深拷贝。

**参数**：

 它**至少需要两个对象**作为参数，第一个参数是目标对象，后面的参数都是源对象。

 如果**只有一个参数，Object.assign会直接返回**该参数。

 如果该参数**不是对象，则会先转成对象，然后返回**。

 由于**undefined和null无法转成对象**，所以如果它们作为参数，就会**报错**。

注：如果目标对象与源对象有**同名属**性，或多个源对象有同名属性，则**后面的属性会覆盖前面的属性**。

注意：如果非对象参数出现在源对象的位置（即**非首参数**），那么处理规则有所不同。首先，这些参数都会转成对象，如果无法转成对象，就会跳过。这意味着， **如果undefined和null不在首参数，就不会报错**。其他类型的值（即数值、字符串和布尔值）不在首参数，也不会报错。但是，除了字符串会以数组形式，拷贝入目标对象，其他值都不会产生效果。

对于**嵌套的对象**，Object.assign的处理方法是替换，而不是添加。

```
var target = { a: { b: 'c', d: 'e' } }
var source = { a: { b: 'hello' } } 
Object.assign(target, source); /*{ a: { b: 'hello' } } */
```

注意，Object.assign可以用**来处理数组，但是会把数组视为对象**。

```
console.log(Object.assign([1, 2, 3], [4, 5]));
/*[4,5,3] 4覆盖1，5覆盖2，因为它们在数组的同一位置，所以就对应位置覆盖了*/
```

如果源对象某个属性的值是对象，那么目标对象拷贝得到的是这个对象的引用。

```
var object1 = { a: { b: 1 } };
var object2 = Object.assign({}, object1); 
object1.a.b = 2; 
console.log(object2.a.b);
```

**用途**：

为对象添加属性；为对象添加方法；克隆对象；合并多个对象；为属性指定默认值

```
//克隆对象：将原始对象拷贝到一个空对象，就得到了原始对象的克隆
function copyFnc(origin) {
	return Object.assign({}, origin)
} 
var sur = { a: 1, b: 2 };
console.log(copyFnc(sur));
```

采用这种方法克隆，只能克隆原始对象自身的值，不能克隆它继承的值。如果想要**保持继承链**，可以采用下面的代码。

```
/*克隆对象：在JS里子类利用Object.getPrototypeOf去调用父类方法,用来获取对象的原型*/
function clone(origin) {
	let originProto = Object.getPrototypeOf(origin);
	return Object.assign(Object.create(originProto), origin);
}
//多个对象合并到某个对象
const merge = (target, ...sources) => Object.assign(target, ...sources);
//多个对象合并到新对象
const merge = (...sources) => Object.assign({}, ...sources);

const o1 = { a: 1 };
const o2 = { b: 2 };
const o3 = { c: 3 };
const obj = Object.assign(o1, o2, o3);// { a: 1, b: 2, c: 3 }
```

#### 7.箭头函数和一般函数有什么区别？

定义箭头函在数语法上要比普通函数简洁得多。箭头函数省去了`function`关键字，采用箭头`=>`来定义函数。

**基本语法：关于箭头函数的参数：**

① 如果箭头函数**没有参数**，直接写一个**空括号**即可。

② 如果箭头函数的**参数只有一个**，也可以**省去包裹参数的括号**。

③ 如果箭头函数有多个参数，将参数依次用逗号(,)分隔，包裹在括号中即可。

**基本语法：关于箭头函数的函数体：**

① 如果箭头函数的函数体只有一句代码，就是简单返回某个变量或者返回一个简单的JS表达式，可以省去函数体的大括号{ }。

② 如果箭头函数的函数体只有一句代码，就是返回一个对象，用小括号包裹要返回的对象，不报错

```
let getTempItem = id => ({ id: id, name: "Temp" });
```

③ 如果箭头函数的函数体只有一条语句并且不需要返回值（最常见是调用一个函数），可以给这条语句前面加一个`void`关键字

```
let fn = () => void doesNotReturn();
//用来简化回调函数：
[1,2,3].map(function (x) {return x * x;});// 正常函数写法
[1,2,3].map(x => x * x);// 箭头函数写法
var result = [2, 5, 1, 4, 3].sort(function (a, b) {  return a - b;});// 正常函数写法
var result = [2, 5, 1, 4, 3].sort((a, b) => a - b);// 箭头函数写法
```

**区别**：

1、语法更加简洁、清晰

2、箭头函数不会创建自己的this，它会捕获自己在**定义时**（注意，是定义时，不是调用时）所处的**外层执行环境的this**，并继承这个`this`值。所以，箭头函数中`this`的指向在它**被定义的时候就已经确定**了，之后永远不会改变。

3、箭头函数继承而来的**this指向永远不变**

4、.call()/.apply()/.bind()**无法改变箭头函数中this的指向**（但是也不会报错）

**5、箭头函数不能作为构造函数使用**：因为箭头函数没有自己的`this`，它的`this`其实是继承了外层执行环境中的`this`，且`this`指向永远不会随在哪里调用、被谁调用而改变，所以箭头函数不能作为构造函数使用，或者说构造函数不能定义成箭头函数，否则用`new`调用时会报错！

**6、箭头函数没有自己的arguments**：在箭头函数中访问`arguments`实际上获得的是外层局部（函数）执行环境中的值。**可以在箭头函数中使用rest参数代替arguments对象，来访问箭头函数的参数列表**

**7、箭头函数没有原型prototype**

```
let sayHi = () => {    console.log('Hello World !')};
console.log(sayHi.prototype); // undefined
```

#### 8.Promise、async await 的使用？

promise和async/await都是异步方案，promise是es6的新特性，而async/await是es7新出的特性。

Promise是一个对象，可以**实现链式的写法**来实现同步异步操作，

**then()…catch()…**，then表示上一个promise执行完后执行，如果出现错误就会传入catch里面，通常这么写：

```
var pro = new promise (function(resolve,reject){
    resolve("success");
    console.log("afterresolve");
    reject("error");
});
pro.then(result=>{
    console.log(result);
});
pro.catch(result=>{
    console.log(result);
})
//afterresolve success
```

**resolve下面的语句其实是可以执行的**，那么为什么reject的状态信息在下面没有接受到呢？

这就是因为Promise对象的特点：**状态的凝固**。new出一个Promise对象时，这个对象的起始状态就是Pending状态，在根据resolve或reject返回Fulfilled状态/Rejected状态。

```
new Promise((resolve, reject) => {
    var param = 'Promise 执行完后返回的数据';
    var error = 'Promise 异步执行异常';
    if( error ) {
        reject(new Error('Promise 异步执行异常'));
    } else {
        resolve(param);
    }
}).then((res) => {
//  这里res就是Promise中的param参数
    console.log(res);  //  Promise 执行完后返回的数据
    var param = '第一个then 执行完后返回的数据';
    return param;
}).then((res) => {
//  这里的res就不是Promise中resolve的param参数了，而是上一个then中的返回值
    console.log(res);  //  第一个then 执行完后返回的数据
}).catch((error) => {
//  这里是Promise执行reject方法中的参数
    console.log(error); //  Promise 异步执行异常
});
```

第一个then()触发条件：是 Promise() 实例化时resolve()触发，resolve(param);

第二个及以后的then() 触发条件是第一个then()执行完成，并且将return值作为下一个then的参数；

**catch()触发条件是执行了reject()**，用于指定发生错误的时候的回调函数。

需要注意的是**resolve与reject只能执行一个**。也就是说如果不加入判断的话，某一个先执行了，后面的就自动忽略了。

对于**async/await**来说是基于promise的，他可以让我们更加优雅的写出代码，而替代then()的写法；

需要注意的就是**await是强制把异步变成了同步，这一句代码执行完，才会执行下一句**。

await必须用在async方法中；处理错误的方法：

![1572012187509](https://codingwithalice.github.io/img/assets_2019/1572012187509.png)

------



# vue相关 面试问题

#### 1. vue实现双向绑定的原理？

MVVM 模式在于数据与视图的保持同步，意思是说数据改变时会自动更新视图，视图发生变化时会更新数据。

 所以我们需要做的就是**如何检测到数据的变化然后通知我们去更新视图**，**如何检测到视图的变化然后去更新数据**。**检测视图这个比较简单，无非就是我们利用事件的监听即可**。那么如何才能知道数据属性发生变化呢？这个就是利用我们上面说到的 `Object.defineProperty` 当我们的属性发生变化时，它会自动**触发 set 函数从而能够通知我们去更新视图**。

数据双向绑定作为 Vue 核心功能之一，Vue 则采用的**是数据劫持与发布订阅相结合的方式实现双向绑定**。

其中数据劫持是利用了 **Object.defineProperty() 方法重新定义了对象获取属性值get和设置属性值set的操作**来实现的；

![preview](https://codingwithalice.github.io/img/assets_2019/v2-0acc539d759e5bf7c4dedb9aafafdb45_r.jpg)

劫持了数据之后，我们就需要一个监听器 Observer 来监听属性的变化。得知属性发生变化之后我们需要一个 Watcher 订阅者来更新视图，我们还需要一个 compile 指令解析器，用于解析我们的节点元素的指令与初始化视图。

- Observer 监听器：用来监听属性的变化通知订阅者
- Watcher 订阅者：收到属性的变化，然后更新视图（这个过程中我们可能会有很多个订阅者 Watcher 所以我们要创建一个容器 Dep 去做一个统一的管理）
- Compile 解析器：解析指令，初始化模版，绑定订阅者

**语法** `Object.defineProperty(obj,prop,descriptor)`

**参数**：obj：目标对象；prop：需要定义的属性或方法的名称；descriptor：目标属性所拥有的特性

**可供定义的特性列表**

| 可供定义的特性 |                                                              |
| :------------- | :----------------------------------------------------------- |
| value          | 属性的值                                                     |
| writable       | 如果为false，属性的值就不能被重写                            |
| get            | 一旦目标属性被访问就会调回此方法，并将此方法的运算**结果返回用户** |
| set            | 一旦**目标属性被赋值**，就会调回此方法                       |
| configurable   | 如果为false，则任何尝试删除目标属性或修改属性性以下特性（writable, configurable, enumerable）的行为将被**无效化**。 |
| enumerable     | 是否能在for…in循环中遍历出来或在Object.keys中列举出来        |

```
var obj = { };
var name;
Object.defineProperty(obj, "data", {
    //获取值
    get:function () {return name;},
    //设置值
    set:function (val) {name = val;console.log(val);}
})
    obj.data = 'aaa';//赋值调用set
   	console.log(obj.data); //取值调用get
```

 当我们**访问或设置**对象的属性的时候，都会**触发相对应的函数**，然后在这个函数里返回或设置属性的值。既然如此，我们当然可以在触发函数的时候动一些手脚做点我们自己想做的事情，这也就是“劫持”操作。

 在Vue中其实就是通过`Object.defineProperty`来**劫持对象属性的`setter`和`getter`操作**，并“种下”一个监听器，**当数据发生变化的时候发出通知**。

注意： **该方法每次只能设置一个属性**，那么就需要遍历对象来完成其属性的配置：

```
Object.keys(student).forEach(key => defineReactive(student, key))
```

 另外还必须是一个**具体的属性**，这也非常的致命。假如后续需要扩展该对象，那么就必须手动为新属性设置 setter 和 getter 方法，**这就是为什么不在 data 中声明的属性无法自动拥有双向绑定效果的原因** 。这时需要调用 `Vue.set() `手动设置。

 **针对 Array 类型的劫持**

 数组是一种特殊的对象，**其下标实际上就是对象的属性，所以理论上是可以采用 `Object.defineProperty()` 方法处理数组对象**。 

 但是 Vue 并没有采用上述方法劫持数组对象，原因分析：1、特殊的 length 属性，相比较对象的属性，数组下标变化地相对频繁，并且改变数组长度的方法也比较灵活，一旦数组的长度发生变化，那么在无法自动感知的情况下，开发者只能手动更新新增的数组下标，这可是一个很繁琐的工作。2、数组主要的操作场景还是遍历，而对于每一个元素都挂载一个 get 和 set 方法，恐怕也是不小的性能负担。

 **数组方法的劫持**：最终 Vue 选择劫持一些**常用的数组操作方法，从而知晓数组的变化情况**：`push', 'pop', 'shift', 'unshift', 'sort', 'reverse', 'splice'`。数组方法的劫持涉及到原型相关的知识，首先数组实例大部分方法都是来源于 `Array.prototype` 对象。顺便提一下，**采用 Vue.set() 方法设置数组元素时，Vue 内部实际上是调用劫持后的 splice() 方法来触发更新**。

**总结**：由上述内容可知，Vue 中的数据劫持分为两大部分：

针对 Object 类型，采用 `Object.defineProperty() `方法劫持属性的读取和设置方法；

针对 Array 类型，采用原型相关的知识劫持常用的函数，从而知晓当前数组发生变化。

并且 `Object.defineProperty()` 方法存在以下**缺陷**：**每次只能设置一个具体的属性**，导致需要遍历对象来设置属性，同时也导致了无法探测新增属性；属性描述符 configurable 对其的影响是致命的。

#### 发布订阅模式

在**观察者**模式中，观察者是知道Subject的，Subject一直保持对观察者进行记录。然而，在**发布订阅**模式中，发布者和订阅者**不知道对方的存在**。它们只有通过消息代理进行通信。

在**发布订阅**模式中，组件是松散耦合的，正好和观察者模式相反。

**观察者模式**大多数时候是**同步**的，比如当事件触发，Subject就会去调用观察者的方法。而**发布-订阅**模式大多数时候是**异步的**（使用消息队列）。

![1568963964686](https://codingwithalice.github.io/img/assets_2019/1568963964686.png)

#### 数据无法双向绑定的情况

**Object.freeze(); 或者 数据未在实例中进行初始化**

```
var obj = {  foo: 'bar'}
Object.freeze(obj)
new Vue({  el: '#app',  data: obj})
```

Object.freeze()方法有三个特点：

1.使对象不可扩展，无法向其添加新属性。

2.为对象的所有属性将 **configurable** 特性设置为 **false**。在 **configurable** 为 **false** 时，无法更改属性的特性且无法删除属性。

3.为对象的所有数据属性将 **writable** 特性设置为 **false**。当 **writable** 为 false 时，无法更改数据属性值。

**数据未在实例中进行初始化**

只有当实例被创建时 `data` 中存在的属性才是**响应式**的。也就是说如果你添加一个新的属性在created生命周期完成后，那么数据将无法进行绑定，如直接使用vm.a=”xxx”，虽然a成了实例的一个属性，但是对它的任何修改将不是响应式的

#### 2. vue组件之间的传值？

1. 父传子： 先在**父组件中绑定变量`<child :msg="parent"></child>`**，parent是定义在父组件中的变量/值； 再在**子组件中添加props属性接收**父组件传递过来的变量`props:['msg']`； 最后就可以在子组件中使用``来表示父组件中parent变量中的值了。

2. 子传父： 先在子组件中**绑定事件`@change="sendChild"`**，触发的时候在`setChild`事件中**用`$emit()`触发父组件中的函数**，并将子组件中的变量作为参数传递；

   ```
   methods：{
       sendChild:function(){
           this.$emit('transparent',this.msg)
       }
   }
   ```

   在父组件中绑定事件`<child @transparent="getChild"></child>`，当子组件触发这个事件的时候，就可以**调用getChild方法获取到传递过来的参数**；

   ```
   methods:{
       getChild(msg){
           this.user=msg;
       }
   }
   ```

   1.兄弟组件互相传值，**通过Vuex状态管理传值**： 先通过npm加载vuex，创建store.js文件

```
//store.js
   import Vue from 'vue'
   import Vuex from 'vuex'
   Vue.use(Vuex);
   const state={name:'Alice'};
   const mutations={
       newName(state,message){
           state.name=message
       }
   }
   export default new Vuex.Store({state,mutations})
```

2.兄弟组件互相传值，引入bus.js文件，发布者订阅者模式：

```
import Bus from './bus.js'
//一个子组件触发
methods:{
  Bus.$emit('触发的方法名'，需要传递的值);
}
//一个子组件监听
   mounted:{
       bus.$on("方法名",(传递的值)=>{ })
   }
```

3.兄弟组件互相传值`$root`

```
//一个子组件触发
this.$root.$emit('触发的方法名'，需要传递的值);
//一个子组件监听
this.$root.$off("方法名");//每次进入先关闭一下
this.$root.$on("方法名",(传递的值)=>{ })
```

#### 3.vue的生命周期有哪些？它们有什么不同？

| 生命周期钩子  | 组件状态                                                     | 响应类型                                                     | 最佳实践                                                     |
| :------------ | :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| beforeCreate  | 实例初始化之后，this指向创建的实例，不能访问到data、computed、watch、methods（都不存在）上的方法和数据 | 拿不到任何信息，无法篡改数据，一般做loding，这个时候的vue实例还什么都没有，但是$route对象是存在的，可以根据路由信息进行重定向之类的操作。 | 常用于初始化非响应式变量                                     |
| created       | 实例创建完成，可访问data、computed、watch、methods上的方法和数据，还未挂载到DOM，不能访问到$el属性，$ref属性内容为空数组 | $el,没有初始化，数据已加载完成，可以篡改数据，并更新，不会触发beforeUpdate，updated，在这结束loading，还做一些初始化，实现函数自执行 ，$ref属性内容为空数组；定义getter、setter存储器属性，在实例创建之后被调用，该阶段可以访问data，**可以使用this**。该阶段允许执行http请求操作。 | 常用于**简单的ajax请求**，页面的初始化                       |
| beforeMount   | 在挂载开始之前被调用，beforeMount之前，会找到对应的template，并编译成render函数 | $el已被初始化，数据已加载完成，阔以篡改数据，并更新，不会触发beforeUpdate，updated。将HTML解析生成AST节点，再根据AST节点动态生成渲染函数。**相关render函数首次被调用**(划重点)。 | -                                                            |
| mounted       | 实例挂载到DOM上，此时可以通过DOM API获取到DOM节点，$ref属性可以访问 | $el已被初始化，数据已加载完成，阔以篡改数据，并更新，并且触发beforeUpdate，updated，在这发起后端请求，拿回数据，配合路由钩子做一些事情；在挂载完成之后被调用，执行render函数生成虚拟dom，创建真实dom替换虚拟dom，并挂载到实例。可以操作dom，比如事件监听 | 常用于获取信息和操作，**ajax请求**                           |
| beforeUpdate  | 响应式数据更新时调用，发生在虚拟DOM打补丁之前                | $vm.data更新之后，虚拟dom重新渲染之前被调用。在这个钩子可以修改$vm.data，并不会触发附加的重渲染过程。 | 适合在**更新之前访问**现有的DOM，比如手动移除已添加的事件监听器 |
| updated       | 虚拟DOM重新渲染和打补丁之后调用，组件DOM已经更新，可执行依赖于DOM的操作 | 虚拟dom重新渲染后调用，若再次修改$vm.data，会再次触发beforeUpdate、updated，进入死循环 | 避免在这个钩子函数中操作数据，可能**陷入死循环**             |
| beforeDestroy | 实例销毁之前调用。这一步，实例仍然完全可用，this仍能获取到实例 |                                                              | **常用于销毁**定时器、解绑全局事件、销毁插件对象等操作       |
| destroyed     | 实例销毁后调用，调用后，Vue实例指示的所有东西都会解绑定，所有的事件监听器会被移除，所有的子实例也会被销毁 |                                                              | -                                                            |

注：

created和mounted之间的区别：

- created和mounted中**ajax请求**的区别：created的时候视图未出现，请求较多的情况下，会出现**白屏**；

- created 是在模板渲染成html前调用，即通常初始化某些属性值，然后再渲染成视图，比如初始化、获取屏幕高度调整、赋值等等；

  而mounted是在模板渲染成html后调用，通常是初始化页面完成后，再对html的dom节点进行一些需要的操作；

1. 初始化组件的时候，仅执行beforeCreated/created/beforeMount/mounted四个钩子函数；

2. 当改变data中定义的**响应式变量**时，会执行beforeUpadate/updated；

3. 初始化和销毁时的钩子函数只会执行一次，beforeUpadate/updated**可执行多次**；

4. 挂载的时候，子组件完成挂载后，父组件才会挂载；

   注意：在传值的时候，如果父组件在mounted传给子组件值，子组件是没有办法在created里面使用的

   father-beforeCreated –> father-created –> son-beforeCreated –>son-created –> son-mounted –>**father-mounted(这是最后一个)**

   father-beforeDestroy –> son-beforeDestroy –> son-destroyed –> father-destroyed

   ![图片描述](https://codingwithalice.github.io/img/assets_2019/156466691112.png)

5. 当子组件完成挂载后，父组件会**主动执行一次**beforeUpdate/updated钩子函数（仅首次）；

6. 销毁父组件时，先将子组件销毁后，才会销毁父组件；

7. 总结来说，虚拟dom开始渲染是在beforeMount时，dom实例挂载完成在mounted阶段显示。那么接下来了解就是render函数。render函数最终返回的是createNodeDescription(节点描述)，即俗称virtual node(虚拟节点)。

#### 4. vuex的功能？能否进行兄弟组件之间的传值？

vuex专为 Vue.js 应用程序开发的**状态管理模式**。它**采用集中式存储管理应用的所有组件的状态**，并以相应的规则保证状态以一种可预测的方式发生变化。

主要用于管理vue中的数据，可以兄弟组件互相传值；

![img](https://codingwithalice.github.io/img/assets_2019/vuex.png)

上图的解释：

① **Vue Components** 是我们的 **vue 组件**，**组件**会触发（dispatch）一些事件或动作( **Actions**); ② 我们在**组件**中发出的动作，肯定是想获取或者改变数据的，但是在 **vuex** 中，数据是集中管理的，我们不能直接去更改数据，所以会把这个动作提交（Commit）到 **Mutations** 中； ③ 然后 **Mutations** 就去改变（Mutate）**State** 中的数据； ④ 当 **State** 中的数据被改变之后，就会重新渲染（Render）到 **Vue Components** (组件)中去， **Vue Components** (组件)展示更新后的数据，完成一个流程。

**Vuex 的核心是 Store**（仓库），相当于是一个容器，一个**Store实例中包含以下属性的方法：**

**state** 定义属性（状态 、数据） **getters** 用来获取属性【就像计算属性，getter 的返回值会根据它的依赖被缓存起来，且只有当它的依赖值发生了改变才会被重新计算；getter 接受 state 作为其第一个参数；】 **actions** 定义方法（动作）【也可以直接修改state，**通过提交 mutation 的方式**，而非直接改变 `this.$store.state.count`，是因为我们想要更明确地追踪到状态的变化；】 **commit** 提交变化，修改数据的唯一方式就是显示的提交 mutations **mutations** 定义变化，处理状态（数据）的改变【操作state中的数据`store.commit('increment')`；】 **mapGetters** 用来获取属性（数据） **mapActions** 用来获取方法（动作）state：管理项目的数据（进行数据初始化）；

#### mutation和action之间有什么区别？怎么写代码修改vuex中的数据？

```
Vuex.Store({
  state,
  actions,
  mutation
});
```

action可以包含任意异步操作，提交的是mutation，而不是直接变更状态；

mutation是同步的。使用`this.$store.commit('xxx')` 来提交mutation。

（下文来自尤大大）

区分 actions 和 mutations 并不是为了解决竞态问题，而是**为了能用 devtools 追踪状态变化**。

事实上在 vuex 里面 actions 只是一个架构性的概念，并不是必须的，说到底只是一个函数，你在里面想干嘛都可以，只要**最后触发 mutation 就行**。异步竞态怎么处理那是用户自己的事情。vuex 真正限制你的只有 **mutation 必须是同步的**这一点（在 redux 里面就好像 reducer 必须同步返回下一个状态一样）。

**同步的意义在于这样每一个 mutation 执行完成后都可以对应到一个新的状态**（和 reducer 一样），这样 devtools 就可以打个 snapshot 存下来，然后就可以随便 time-travel 了。

如果你开着 devtool 调用一个异步的 action，你可以清楚地看到它所调用的 mutation 是何时被记录下来的，并且可以立刻查看它们对应的状态。

```
<div id="app1">
    8
</div>
//store.js
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

const store = new Vuex.Store({
    state:{
        count:0
    }
});

new Vue({
    el:'#app1',
    store,
    computed:{
        count(){
            return this.$store.state.count
        }
    }
})
```

#### vuex的使用

需要在根实例main.js中传入store

```
import store from './store'
import 'styles/reset.css'
import 'styles/border.css'
import 'styles/iconfont.css'
import 'swiper/dist/css/swiper.css'

Vue.config.productionTip = false
fastClick.attach(document.body)
Vue.use(VueAwesomeSwiper)

new Vue({
  el: '#app',
  router,
  store,
  components: { App },
  template: '<App/>'
})
```

写在一个页面上的话，需要判断本地是否已经有这个数据了

![1567605439082](https://codingwithalice.github.io/img/assets_2019/1567605439082.png)

在src–store–index.js中声明state、mutations

```
import Vue from 'vue'
import Vuex from 'vuex'
import state from './state'
import mutations from './mutations'

Vue.use(Vuex)

export default new Vuex.Store({
  state,
  mutations
})
```

然后在src–store–state.js中声明公共使用的数据

```
let defaultCity = '上海'
try {
  if (localStorage.city) {
    defaultCity = localStorage.city
  }
} catch (e) {}

export default {
  city: defaultCity //调用的时候，调用city就可以了
}
```

在src–store–mutations.js中声明改变公共变量的方法

```
export default {
  changeCity (state, city) { //调用的时候使用changeCity就可以了
    state.city = city
    try {
      localStorage.city = city
    } catch (e) {}
  }
}
```

在实际使用的页面中，就可以直接使用了

```
// 调用数据
this.$store.state.city
//修改store中的内容
this.$store.dispatch('name',value)
//或者直接使用commit进行修改
this.$store.commit('name',value)
```

#### 5. Axios调取数据？

[页面直接引用 `<script src="https://unpkg.com/axios/dist/axios.min.js"></script>`]

#### axios的特性

1.可以从浏览器中创建XHR对象 2、可以从nodeJS中创建HTTP请求 3、支持Promise 4、可以拦截请求和响应 5、可以转换请求数据和响应数据 6、可以取消请求 7、可以自动转换JSON数据 8、客户端支持防御XSRF

**axios get 方法**：仅仅请求后台数据

```
axios.get('index.php')
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

**aixos post方法**：post请求更多的是要提交数据，params属性里的数据会出现在请求主体中。

```
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

**多并发请求,一次性发几个请求**

```
function getUserAccount() {
  return axios.get('/user/12345');
}

function getUserPermissions() {
  return axios.get('/user/12345/permissions');
}

axios.all([getUserAccount(), getUserPermissions()])
  .then(axios.spread(function (acct, perms) {
    // acct为第一个请求的结果，perms为第二个请求的结果
  }));
```

**设置拦截器**：

```
//请求拦截器
		axios.interceptors.request.use(  
        config => {
            btn.innerHTML='请求数据中';
            return config;
        },
        // 错误时发生的事情
        err => {
            console.log(err)
        });
 // 响应应拦截器
        axios.interceptors.response.use(
        config => {
            btn.innerHTML='请求数据成功';
            return config;
        },
        // 错误时发生的事情
        err => {
            console.log(err)
        });
```

**设置自定义请求头**：

先安装Axios：`npm install axios --save`

再在main.js中引入Axios：

```
import axios from 'axios'
Vue.prototype.$http = axios;
```

即可在组件中调用Axios：

```
this.$axios.get('index.php/url')
  .then(response => {
    console.log(response)
  }).catch(error => {
    console.log(error)
  });
```

然后设置自定义的头请求：

```
axios.defaults.timeout = 5000;//请求超时的时间设定
axios.defaults.headers.post['Content-Type'] = 'application/json'; //axios默认的请求方式
axios.defaults.baseURL = 'http://localhost:8008';//axios默认的请求地址
axios.defaults.headers.common["token"] = "noname";//有些接口必须登录才可以调用，而登陆注册并未写好，后台给了一个故固定的token，写在了头里面
```

#### 6. vue使用的UI框架？

**animate.css**是一款前端动画库，相似的有velocity-animate；

（element ui框架的按钮组件；

 iView 是一套基于 Vue.js 的开源 UI 组件库，主要服务于 PC 界面的中后台产品

 Vuetify.js根据材料设计规格提供 UI 布局；

 基于 Vue.js 的 Bootstrap 组件；

 cube-ui 是滴滴团队开发的基于 Vue.js 实现的精致移动端组件库；

 vue-beauty 是一套基于 vue.js 和 ant-design样式 的PC端 UI 组件库；

 AT-UI 是一个模块化的前端 UI 框架，基于Vue.js 的快速和强大的 Web 界面；专门为桌面应用程序构建；

 Vue-Blu是基于Vue.js和Bulma开发的开源UI组件库。旨在为PC端的前端开发(特别是中后台产品)提供一个快速且灵活的解决方案。）

**使用步骤：**

1. **首先`npm install animate.css --save`；**
2. 然后在vue文件的script中**引入`import animate from 'animate.css'`；**
3. 最后**绑定元素使用**，如下：

```
<template>
    <div class="song">
        <p id="f" @click='fade'>hello</p>
    </div>
</template>
methods:{
    fade:function(){
        $('#f').addClass('animated bounceOutLeft')
    }
}
```

部分api常见：

```
	fade: {
        title: '淡入淡出',
        fadeIn: '淡入',
        fadeOut: '淡出',
      },
      bounce: {
        title: '弹跳类',
        bounceIn: '弹跳进入',
        bounceOut: '弹跳退出',
      },
      zoom: {
        title: '缩放类',
        zoomIn: '放大进入',
        zoomOut: '缩小退出',

      },
      rotate: {
        title: '旋转类',
        rotateIn: '顺时针旋转进入',
      },
      flip: {
        title: '翻转类',
      },
      strong: {
        title: '强调类',
        bounce: '弹跳',
        flash: '闪烁',
      }
```

#### 7.v-if和v-show之间的区别？

 相同点：v-if与v-show都可以动态控制dom元素显示隐藏

 不同点：

实现**本质方法**区别

- vue-show本质就是标签`display:为none;`，控制隐藏，DOM结构是一直存在的
- vue-if是动态的向DOM树内**添加或者删除DOM元素**

编译的区别

- v-show其实就是在**控制css**
- v-if切换有一个局部编译/卸载的过程，切换过程中合适地**销毁和重建内部的事件监听和子组件**

编译的条件

- v-show**都会编译**，初始值为false，只是将display设为none，但它也编译了
- v-if初始值为false，就不会编译了

性能

- v-show只编译一次，后面其实就是控制css，而v-if不停的销毁和创建，故**v-show性能更好一点**。

#### 8.v-for中key值的作用？

 key的作用主要是为了**高效的更新虚拟DOM**。另外vue中在使用相同标签名元素的过渡切换时，也会使用到key属性，其目的也是为了让vue可以**区分它们**，否则vue只会替换其内部属性而不会触发过渡效果。

 在用v-for更新已渲染的元素列表的时候，会使用**就地复用**的策略；这就是说列表数据修改的时候，他会根据key值去判断某个值是否修改，如果修改了就重新渲染，不然就复用之前的元素。

#### 9.vue中插槽的作用？

 插槽就是Vue实现的一套**内容分发的API**，将`<slot></slot>`元素作为承载分发内容的出口，没有插槽的情况下在组件标签内些一些内容是不起任何作用的。

 插槽内可以是任意内容。在`<child-component>你好</child-component>`内放置一些内容，输出内容还是在组件中的内容，直接在父组件的` <child-component>`标签中定义的内容不会被渲染。**在子组件template中加入`<slot>`元素占位，便能渲染父组件`<child>`标签下的内容**。

 **具名插槽**，当需要多个插槽时，可以使用`<slot>`的特性：name。这个特性可以用来定义额外的插槽。

```
	<div id="root">
        <child>
            <header slot="header">header</header>
            <footer slot="footer">footer</footer>
        </child>
    </div>
       Vue.component('child',{
            template:`<div>
                            <slot name="header">default header</slot>
                            <div>content</div>
                            <slot name="footer">default footer</slot>
                        </div>`
            }
        )
        var vm=new Vue({
            el:'#root'
        })
 //输出结果是 header   content   footer
```

 **插槽默认内容** ，插槽可以提供一个默认内容，如果如果父组件没有为这个插槽提供了内容，会显示默认的内容。如果父组件为这个插槽提供了内容，则默认的内容会被替换掉。

 **作用域插槽**，作用域插槽就是父组件在**调用子组件的时候给子组件传了一个插槽**，这个插槽为作用域插槽，该插槽必须放在template标签里面，同时声明从子组件接收的数据放在一个自定义属性内，并定义该数据的渲染方式。（解决的问题：调用了两次child组件，因为调用的是同一个子组件，所以显示的内容完全一样。如何在每次调用时能有各自的渲染效果？）

```
	<div id="root">
        <child>
            <template slot-scope="props"><!--该插槽必须放在template标签内-->
                <li></li> <!--定义渲染方式-->
            </template>
        </child>
        <child>
            <template slot-scope="props">
                <h1></h1><!--定义渲染方式-->
            </template>
        </child>
    </div>
Vue.component('child',{
            data: function(){
                return {
                    list:[1,2,3,4]
                }
            },
            template: `<div>
                            <ul>
                                <slot v-for="value in list" :value=value>//使用slot占位
                                </slot>
                            </ul>
                        </div>`
        })
        var vm=new Vue({
            el: '#root'
        })
```

#### 10.vue中watch和computed有什么区别？分别在哪种场合下使用？监听的是data里面的值吗？

| computed 计算属性                                            | watch 观察的动作                                             | methods                          |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :------------------------------- |
| 1. 数据会被缓存，只要依赖不发生改变，即使页面重新渲染，该方法也不会被调用 2.computed中的函数必须用return返回 | 1. 直接监测一个值的变化，监测值不发生变化，该方法就不会调用； 2. watch只会监听数据的值是否发生改变，而不会去监听数据的地址是否发生改变。也就是说，watch想要监听引用类型数据的变化，需要进行深度监听。 3.watch中的函数有两个参数，前者是newVal，后者是oldVal。 | 每次页面发生渲染，都会被重新调用 |
| 在computed中不要对data中的属性进行赋值操作。如果对data中的属性进行赋值操作了，就是data中的属性发生改变，从而触发computed中的函数，形成死循环了。 | 监听复杂数据类型需用深度监听（在被监听对象中使用`handler`）；特殊情况下，watch无法监听到数组的变化，特殊情况就是说更改数组中的数据时，数组已经更改，但是视图没有更新。**更改数组必须要用splice()或者$set**。 |                                  |
| 使用场景：**当一个值受多个属性影响的时候————购物车商品结算** | 使用场景：**当一条数据的更改影响到多条数据的时候———搜索框**  |                                  |

**computed和watch区别：**

1、 功能上：computed是计算属性，也就是依赖其它的属性计算所得出最后的值，是用于定义**基于数据之上的数据**。watch是监听一个值的变化，然后执行对应的回调，是在**某个数据变化时做一些事情**。

2、 **是否调用缓存**：computed中的函数所依赖的属性没有发生变化，那么调用当前的函数的时候会从缓存中读取，而watch在每次监听的值发生变化的时候都会执行回调。

3、 **是否调用return**：computed中的函数必须要用return返回，watch中的函数不是必须要用return。

4、 如果一个值依赖多个属性（多对一），用`computed`肯定是更加方便的。如果一个值变化后会引起一系列操作，或者一个值变化会引起一系列值的变化（一对多），用`watch`更加方便一些。

#### 11.数据请求应该添加在生命周期的哪里？

 看实际情况，一般在 created（或beforeRouter） 里面就可以，如果涉及到需要页面加载完成之后的话就用 mounted。主要的区分在于**是否需要操作DOM结构**。 1.在created的时候，视图中的html并没有渲染出来，所以此时如果直接去操作html的dom节点，一定找不到相关的元素； 2.而在mounted中，由于此时html已经渲染出来了，所以可以直接操作dom节点，（此时document.getelementById 即可生效了）；

#### 12.vue组件中data为什么是函数

是因为js本身的特性带来的，跟vue本身设计无关。类比引用数据类型：Object是引用数据类型,如果不用function 返回,每个组件的data 都是内存的同一个地址,一个数据改变了其他也改变了;

```
//如果直接赋值，两个实例同时引用一个对象，那么当你修改其中一个属性的时候，另外一个实例也会跟着改
var MyComponent = function() {}
MyComponent.prototype.data = {
  a: 1,
  b: 2,
}
// 上面是一个虚拟的组件构造器，真实的组件构造器方法很多

var component1 = new MyComponent()
var component2 = new MyComponent()
// 上面实例化出来两个组件实例，也就是通过<my-component>调用，创建的两个实例

component1.data.a === component2.data.a // true
component1.data.b = 5;
component2.data.b // 5
Vue.component('my-component', {
  template: '<div>OK</div>',
  data() {
    return {} // 返回一个唯一的对象，不要和其他组件共用一个对象进行返回
  },
})
```

data是一个函数时，每个组件实例都有自己的作用域，每个实例相互独立,不会相互影响；

#### 13.多页应用与单页应用的区别？以及优缺点

**多页应用：**

- 定义：每一次页面的跳转，后端都会返回一个新的html文件。

优点：1. **首屏事件快**（只请求 html 文件就可以展示页面了，只经历了一个http请求）；2. SEO（**搜索引擎优化**，可以识别 html 内的内容）效果好。

缺点：页面切换**慢**（每次跳转都要发送一个http请求）

**单页应用：**

- 定义：每一次页面的跳转，都是使用`JS`渲染。页面跳转不使用 a 标签，而是使用`<router-link to="./list"></router-link>`，不请求`html`文件，通过`JS`感知到`URL`的变化，可以用`JS`动态得把当前页面清除掉，再把下一个页面挂载到当前页面上。

优点：页面切换**快**。不需要http请求。

缺点：首屏时间稍慢（除了请求一个html文件，还要请求一个 JS 文件）; SEO差（不认识JS文件中的内容）

#### 13.vue router[路由守卫]有哪些钩子函数，哪一个是可以在全局使用的

主要用来作用是**拦截导航，让他完成跳转或取消**。

**完整的导航解析流程**

1. 导航被触发。
2. 在失活的组件里调用离开守卫。
3. 调用全局的 `beforeEach` 守卫。
4. 在重用的组件里调用 `beforeRouteUpdate` 守卫 (2.2+)。
5. 在路由配置里调用 `beforeEnter`。
6. 解析异步路由组件。
7. 在被激活的组件里调用 `beforeRouteEnter`。
8. 调用全局的 `beforeResolve` 守卫 (2.5+)。
9. 导航被确认。
10. 调用全局的 `afterEach` 钩子。
11. 触发 DOM 更新。
12. 用创建好的实例调用 `beforeRouteEnter` 守卫中传给 `next` 的回调函数。

**有三种方式可以植入路由导航过程中：**全局的；单个路由独享的；组件级的

**①.全局**导航钩子

1. router.beforeEach **全局前置守卫** 进入路由之前
2. router.beforeResolve 全局解析守卫(2.5.0+) 在beforeRouteEnter调用之后调用
3. router.afterEach 全**局后置钩子** 进入路由之后

```
    // main.js 入口文件
    import router from './router'; // 引入路由
    router.beforeEach((to, from, next) => { 
      next();
    });
    router.beforeResolve((to, from, next) => {
      next();
    });
    router.afterEach((to, from) => {
      console.log('afterEach 全局后置钩子');
    });
```

这三个参数 to 、from 、next 分别的作用：

**to**: Route，代表**要进入的目标**，它是一个路由对象；路由对象指的是平时通过**this.$route获取到的路由对象**。

**from**: Route，代表当前**正要离开的路由**，同样也是一个路由对象

**next**: Function，这是一个**必须需要调用的方**法，而具体的执行效果则依赖 next 方法调用的参数

 **next()**：进入该路由。进入管道中的下一个钩子，如果全部的钩子执行完了，则导航的状态就是 confirmed（确认的） **next(false)**：取消进入路由，这代表中断掉当前的导航，即 to 代表的路由对象不会进入，被中断，此时该表 URL 地址会被重置到 from 路由对应的地址(也就是将要离开的路由地址)。 **next(‘/’)** 和 **next({path: ‘/’})**：在中断掉当前导航的同时，跳转到一个不同的地址 **next(error)**：如果传入参数是一个 Error 实例，那么导航被终止的同时会将错误传递给 router.onError() 注册过的回调 注意：next 方法必须要调用，否则钩子函数无法 resolved

不同于前置守卫，后置钩子并没有 next 函数，也不会改变导航本身

**②.路由独享的钩子**：即单个路由独享的导航钩子，它是在**路由配置上直接进行定义**的

```
const router = new VueRouter({
    routes: [{
            path: '/file',
            component: File,
            beforeEnter: (to, from ,next) => {/*do someting*/}
        }]
});
```

**③.组件内的导航钩子**：`beforeRouteEnter`、`beforeRouteUpdate`、`beforeRouteLeave`。直接在路由组件内部直接进行定义的

```
const File = {
    template: `<div>This is file</div>`,
    beforeRouteEnter(to, from, next) {
        // do someting
        // 在渲染该组件的对应路由被 confirm 前调用
    },
    beforeRouteUpdate(to, from, next) {
        // do someting
        // 在当前路由改变，但是依然渲染该组件是调用
    },
    beforeRouteLeave(to, from ,next) {
        // do someting
        // 导航离开该组件的对应路由时被调用
    }
}
```

注意：`beforeRouteEnter` **不能获取组件实例 this**，因为当守卫执行前，组件实例被没有被创建出来，剩下两个钩子则可以正常获取组件实例 this；但是并不意味着在` beforeRouteEnter `中无法访问组件实例，我们可以通过给 next 传入一个回调来访问组件实例。在导航被确认是，会执行这个回调，这时就可以访问组件实例了：

```
//注意，仅仅是 beforRouteEnter 支持给 next 传递回调，其他两个并不支持。因为归根结底，支持回调是为了解决 this 问题，而其他两个钩子的 this 可以正确访问到组件实例，所有没有必要使用回调
beforeRouteEnter(to, from, next) {
    next (vm => {/*这里通过 vm 来访问组件实例解决了没有 this 的问题*/})
}
```

#### 14.data为什么要用return？不是为了使每个组件有独立的数据？（摘自vue官方文档）

当一个**组件**被定义，`data` 必须声明为返回一个初始数据对象的函数，因为组件可能被用来创建多个实例。如果 `data` 仍然是一个纯粹的对象，则所有的实例将**共享引用**同一个数据对象！通过提供 `data` 函数，每次创建一个新实例后，我们能够调用 `data` 函数，从而返回初始数据的一个全新副本数据对象。

#### 15.vue中的定时器，一般在哪个生命周期中清除

在beforeDestroy（）里面清除定时器，

```
beforeDestroy() {
    clearInterval(this.timer);        
    this.timer = null;
}
```