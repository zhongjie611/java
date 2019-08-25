## 简单服务返回字符和返回html

1. 下载node.js不停下一步 完成

2. 创建js文本

   示例 http-url-res.js

   	var http = require('http')
   	var url = require("url");
   	var querystring = require("querystring");
   	// 1. 创建 Server
   	var server = http.createServer()
   	
   	// 2. 监听 request 请求事件，设置请求处理函数
   	server.on('request', function (req, res) {
   	  console.log('收到请求了，请求路径是：' + req.url)
   	
   	//获取返回的url对象的query属性值 
   		var arg = url.parse(req.url).query;
   		
   		//将arg参数字符串反序列化为一个对象
   		var params = querystring.parse(arg);
   		//请求的方式
   		console.log("method - " + req.method);
   		//请求的url
   		console.log("url - " + req.url);
   		//获取参数param
   		console.log("param - " + params.param);
   		   //设置允许跨域的域名，*代表允许任意域名跨域
   	   res.setHeader("Access-Control-Allow-Origin","http://www.zhangpeiyue.com");
   	   //允许的header类型
   	   res.setHeader("Access-Control-Allow-Headers","content-type");
   	   //跨域允许的请求方式 
   	   res.setHeader("Access-Control-Allow-Methods","DELETE,PUT,POST,GET,OPTIONS");
   		if(params.param == "html"){
   			  var ht = "<!DOCTYPE html>" +
   				"<html lang='zh-CN'>" +
   				  "<head>" +
   					"<meta name='viewport' content='width=device-width, initial-scale=1'>" +
   					"<meta http-equiv='X-UA-Compatible' content='IE=Edge'>" +
   					"<meta charset='UTF-8'>" +
   					"<title>TITLE</title>" +
   				  "</head>" +
   				  "<body>" +
   					"<h1>hello node.js</h1>" +
   				  "</body>" +
   				"<html>";
   			res.write(ht)
   		}else if(params.param=="json"){
   			//中文乱码
   			res.writeHead(200, {'Content-Type': 'text/plain;charset=utf-8'})
   		    var products = [{
   				name: '苹果 X',
   				price: 8888
   			  },
   			  {
   				name: '菠萝 X',
   				price: 5000
   			  },
   			  {
   				name: '小辣椒 X',
   				price: 1999
   			  }
   			]
   			res.write(JSON.stringify(products))
   		}
   	 	res.end()
   	
   	    // 响应内容只能是二进制数据或者字符串
   	    //  数字
   	    //  对象
   	    //  数组
   	    //  布尔值
   	})
   	
   	// 3. 绑定端口号，启动服务
   	server.listen(3000, function () {
   	  console.log('服务器启动成功，可以访问了。。。')
   	})

    

3. node 文本名启动服务

   node http-url-res.js

4. 直接localhost端口访问

