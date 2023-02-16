​	

# JDBC

## 第一节课

![image-20221106102231001](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221106102231001.png)

![image-20221106103358103](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221106103358103.png)

## 第一天

![image-20221127234413444](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221127234413444.png)

![image-20221127234942719](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221127234942719.png)

![image-20221127235550802](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221127235550802.png)

![image-20221127235722578](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221127235722578.png)

![image-20221128000202388](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221128000202388.png)

![image-20221128000259332](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221128000259332.png)

1. ascll：只占一个字节

	gbk：字母数字占一个字节，汉字占两个字节

	utf-8：字母数字占一个字节，汉字占三个字节（110xxxxx 10xxxxxx 10xxxxxx）

2. 一致

3. 不会，因为很多字符集都兼容了ascll码

![image-20221128000911916](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221128000911916.png)

![image-20221128001139804](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221128001139804.png)

![image-20221128001325782](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221128001325782.png)

![image-20221128001520914](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221128001520914.png)

![image-20221128001550390](https://cdn.jsdelivr.net/gh/yzk656/image/image-20221128001550390.png)

# Servlet

## 2023-02-03

![image-20230203161932288](https://cdn.jsdelivr.net/gh/yzk656/image/202302031619354.png)

![image-20230203163422451](https://cdn.jsdelivr.net/gh/yzk656/image/202302031634518.png)

![image-20230203163722848](https://cdn.jsdelivr.net/gh/yzk656/image/202302031637903.png)

![image-20230203165840355](https://cdn.jsdelivr.net/gh/yzk656/image/202302031658390.png)

![image-20230203165917593](https://cdn.jsdelivr.net/gh/yzk656/image/202302031659616.png)

## 2023-02-04

![image-20230204121347016](https://cdn.jsdelivr.net/gh/yzk656/image/202302041213088.png)

![image-20230204121430003](https://cdn.jsdelivr.net/gh/yzk656/image/202302041214033.png)

![image-20230204170908413](https://cdn.jsdelivr.net/gh/yzk656/image/202302041709504.png)

![image-20230204171242274](https://cdn.jsdelivr.net/gh/yzk656/image/202302041712304.png)

![image-20230204171521459](https://cdn.jsdelivr.net/gh/yzk656/image/202302041715490.png)

![image-20230204173459294](https://cdn.jsdelivr.net/gh/yzk656/image/202302041734335.png)

![image-20230204181854481](https://cdn.jsdelivr.net/gh/yzk656/image/202302041818542.png)

![image-20230204181954627](https://cdn.jsdelivr.net/gh/yzk656/image/202302041819689.png)

![image-20230204182044183](https://cdn.jsdelivr.net/gh/yzk656/image/202302041820232.png)

![image-20230204191605363](https://cdn.jsdelivr.net/gh/yzk656/image/202302041916406.png)

![image-20230204191816652](https://cdn.jsdelivr.net/gh/yzk656/image/202302041918705.png)

![image-20230204191826164](https://cdn.jsdelivr.net/gh/yzk656/image/202302041918211.png)

## 2023-02-05

![image-20230204214536283](https://cdn.jsdelivr.net/gh/yzk656/image/202302042145328.png)

![image-20230204214636950](https://cdn.jsdelivr.net/gh/yzk656/image/202302042146019.png)

```js
//service方法会自动判断是 Get 还是 Post 请求



package com.yzk.servlet;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

@WebServlet("/ser04")
public class servlet04 extends HttpServlet {
//    @Override
//    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
//        System.out.println("service ...");
//    }

    /**
     * Get 请求调用
     * @param req
     * @param resp
     * @throws ServletException
     * @throws IOException
     */
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("Get 请求");
    }

    /**
     * Post 请求调用
     * @param req
     * @param resp
     * @throws ServletException
     * @throws IOException
     */
    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("Post 请求");
        /*调用 Get 请求*/
        doGet(req, resp);
    }
}
```

![image-20230205122445341](https://cdn.jsdelivr.net/gh/yzk656/image/202302051224460.png)

![image-20230205122801173](https://cdn.jsdelivr.net/gh/yzk656/image/202302051228225.png)

![image-20230205124402292](https://cdn.jsdelivr.net/gh/yzk656/image/202302051244335.png)

![image-20230205124412640](https://cdn.jsdelivr.net/gh/yzk656/image/202302051244683.png)

![image-20230205124607018](https://cdn.jsdelivr.net/gh/yzk656/image/202302051246052.png)

```java
package com.yzk.servlet;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * @ClassName: servlet05
 * @Description: TODO
 * @Author: 杨振坤
 * @date: 2023/2/5 12:31
 */

@WebServlet("/ser05")
public class servlet05 extends HttpServlet {

    /**
     * 就绪/服务方法（处理请求数据）
     * 系统方法，服务器自动调用
     * 当有请求到达 Servlet 容器时，就会调用该方法（可以被多次调用）
     * @param req
     * @param resp
     * @throws ServletException
     * @throws IOException
     */
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("servlet 被调用了");
    }

    /**
     * 销毁方法
     * 系统方法，服务器自动调用
     * 当服务器关闭或应用程序停止时，调用该方法
     * 方法只会执行一次
     */
    @Override
    public void destroy() {
        System.out.println("servlet 被销毁了");
    }

    /**
     * 初始化方法
     * 系统方法，服务器自动调用
     * 当请求到达 Servlet 容器时，Servlet容器会自动判断该 Servlet 对象是否存在，如果不存在，则创建实例并初始化
     * 方法只会执行一次
     * @throws ServletException
     */
    @Override
    public void init() throws ServletException {
        System.out.println("servlet 被创建了");
    }
}
```

![image-20230205124658577](https://cdn.jsdelivr.net/gh/yzk656/image/202302051246622.png)

![image-20230205125029327](https://cdn.jsdelivr.net/gh/yzk656/image/202302051250390.png)

![image-20230205145355908](https://cdn.jsdelivr.net/gh/yzk656/image/202302051453014.png)

```java
package com.yzk.servlet;


import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * @ClassName: servlet01
 * @Description: TODO
 * @Author: 杨振坤
 * @date: 2023/2/5 14:00
 */
@WebServlet("/ser01")
public class servlet01 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*常用方法*/
        /*获取请求头的完整路径 （从http开始，到“？”前面结束）*/
        String url = req.getRequestURL().toString();
        System.out.println(url);
        /*获取请求时的部分路径 （从项目的站点开始，到 ？ 前面结束）*/
        String uri = req.getRequestURI();
        System.out.println(uri);
        /*获取请求时的参数字符串 （从 ？ 后面开始，到最后的字符串）*/
        String queryString = req.getQueryString();
        System.out.println(queryString);
        /*获取请求方式 （Get和Post）*/
        String method = req.getMethod();
        System.out.println(method);
        /*获取当前协议版本 （Http/1.1）*/
        String protocol=req.getProtocol();
        System.out.println(protocol);
        /*获取项目的站点名 （项目对外访问路径）*/
        String webapp=req.getContextPath();
        System.out.println(webapp);


        /*获取指定名称的参数值*/
        String uname=req.getParameter("uname");
        String upwd=req.getParameter("upwd");

        System.out.println(uname+" "+upwd);

        /*获取指定名称参数的所有参数值，返回字符串数组（用于复选框传值）*/
        String[] hobbys=req.getParameterValues("hobby");
        /*判断数组是否为空*/
        if(hobbys!=null&&hobbys.length>0){
            for(String hobby:hobbys){
                System.out.println(hobby);
            }
        }
    }
}
```

![image-20230205151838317](https://cdn.jsdelivr.net/gh/yzk656/image/202302051518371.png)

==Tomcat10.1.x发布，告别中文乱码==

目前post请求中文乱码也已经没了

![image-20230205163019615](https://cdn.jsdelivr.net/gh/yzk656/image/202302051630674.png)

```java
package com.yzk.servlet;

/**
 * @ClassName: servlet03
 * @Description: 请求转发跳转
 * @Author: 杨振坤
 * @date: 2023/2/5 16:33
 */

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * 可以让请求从服务端跳转到客户端（或跳转到指定的 Servlet）
 * 这个是服务端行为
 *
 * 特点：
 *  1. 服务端行为
 *  2. 地址栏不变
 *  3. 从始至终只有一个请求
 *  4. req数据可以共享
 */
@WebServlet("/ser03")
public class servlet03 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*接收客户端请求参数*/
        String uname = req.getParameter("uname");
        System.out.println("servlet03 " + uname);

        /*请求转发跳转Servlet04*/
//        req.getRequestDispatcher("ser04").forward(req, resp);

        /*请求转发跳转到 jsp 页面*/
//        req.getRequestDispatcher("login.jsp").forward(req,resp);
        /*请求转发跳转到 HTML 页面*/
        req.getRequestDispatcher("login.html").forward(req,resp);
    }
}
```

![image-20230205165249870](https://cdn.jsdelivr.net/gh/yzk656/image/202302051652908.png)

```java
package com.yzk.servlet;

/**
 * @ClassName: servlet03
 * @Description: request作用域
 * @Author: 杨振坤
 * @date: 2023/2/5 16:33
 */

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;
import java.util.ArrayList;
import java.util.List;


@WebServlet("/ser05")
public class servlet05 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("servlet05。。。 ");

        /*设置域对象内容*/
        req.setAttribute("name", "admin");
        req.setAttribute("age", 20);
        List<String> list = new ArrayList<>();
        list.add("aaa");
        list.add("bbb");
        req.setAttribute("list", list);

        /*进行请求转发*/
//        req.getRequestDispatcher("ser06").forward(req,resp);
        req.getRequestDispatcher("index.jsp").forward(req,resp);
    }
}

```



jsp

```jsp
<%@ page import="java.util.List" %>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>$Title$</title>
</head>
<body>
<h2>index页面</h2>
<%--如果要在jsp中写 Java 代码，需要写在脚本段中<%%>--%>
<%
    /*获取域对象内容*/
    String name=request.getAttribute("name").toString();
    Integer age=(Integer) request.getAttribute("age");
    List<String> list=(List<String>) request.getAttribute("list");
    System.out.println(name);
    System.out.println(age);
    System.out.println(list);
%>
</body>
</html>

```

![image-20230205194838464](https://cdn.jsdelivr.net/gh/yzk656/image/202302051948537.png)

![image-20230205213050745](https://cdn.jsdelivr.net/gh/yzk656/image/202302052130792.png)

```java
package com.yzk.servlet1;

/**
 * @ClassName: servlet01
 * @Description: Response
 * @Author: 杨振坤
 * @date: 2023/2/5 21:34
 */

import jakarta.servlet.ServletException;
import jakarta.servlet.ServletOutputStream;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;
import java.io.PrintWriter;

/**
 * 响应数据
 *  getWriter()         字符输出流【输出字符串】
 *  getOutputStream（）  字节输出流【输出一切数据】
 *  两种流不能同时使用，否则会报错
 */
@WebServlet("/ser001")
public class servlet01 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
/*        *//*获取字符输出流*//*
        PrintWriter writer=resp.getWriter();
        *//*输出数据*//*
        writer.write("hello");*/

        /*获取字节输出流*/
        ServletOutputStream out=resp.getOutputStream();
        out.write("hi".getBytes());
    }
}
```

![image-20230205221208103](https://cdn.jsdelivr.net/gh/yzk656/image/202302052212174.png)

```java
package com.yzk.servlet1;

/**
 * @ClassName: servlet01
 * @Description: 乱码问题
 * @Author: 杨振坤
 * @date: 2023/2/5 21:34
 */

import jakarta.servlet.ServletException;
import jakarta.servlet.ServletOutputStream;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.*;

/**
 * 字符响应流
 * 乱码解决
 * 1. 设置服务端编码格式、
 * 2. 设置客户端编码格式
 * 总结：设置客户端和服务端编码格式都支持中文，且保持一致
 */
@WebServlet("/ser002")
public class servlet02 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
//        /*设置服务端的编码格式*/
//        resp.setCharacterEncoding("UTF-8");
//        /*设置客户端编码格式*/
//        resp.setHeader("content-type", "text/html;charset=UTF-8");

        /*简洁模式*/
        resp.setContentType("text/html;charset=UTF-8");

        //*获取字符输出流*//
        PrintWriter writer = resp.getWriter();
        //*输出数据*//
        writer.write("<h2>你好</h2>");
    }
}
```

![image-20230205223514590](https://cdn.jsdelivr.net/gh/yzk656/image/202302052235658.png)

```java
package com.yzk.servlet1;

/*
 * @ClassName: servlet01
 * @Description: Response
 * @Author: 杨振坤
 * @date: 2023/2/5 21:34
 */

import jakarta.servlet.ServletException;
import jakarta.servlet.ServletOutputStream;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * 字节响应数据
 * 乱码解决
 * 1. 设置服务端编码格式、
 * 2. 设置客户端编码格式
 * 总结：设置客户端和服务端编码格式都支持中文，且保持一致
 * */
@WebServlet("/ser003")
public class servlet03 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*简洁模式*/
        resp.setContentType("text/html;charset=UTF-8");
        /*获取字节输出流*/
        ServletOutputStream out=resp.getOutputStream();
        out.write("<h2>你好</h2>".getBytes("UTF-8"));
    }
}
```

![image-20230205223913662](https://cdn.jsdelivr.net/gh/yzk656/image/202302052239715.png)

```java
package com.yzk.servlet1;

/*
 * @ClassName: servlet01
 * @Description: 重定向
 * @Author: 杨振坤
 * @date: 2023/2/5 21:34
 */

import jakarta.servlet.ServletException;
import jakarta.servlet.ServletOutputStream;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * 1. 服务端指导，客户端行为
 * 2. 存在两次请求
 * 3. 地址栏会发生改变
 * 4. request对象不共享
 * */
@WebServlet("/ser004")
public class servlet04 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("servlet004");

        /*接收参数*/
        String uname=req.getParameter("uname");
        System.out.println("ser004 "+uname);

        /*重定向跳转到ser005*/
        resp.sendRedirect("ser005");
    }
}

```

```java
package com.yzk.servlet1;

/*
 * @ClassName: servlet01
 * @Description: 重定向
 * @Author: 杨振坤
 * @date: 2023/2/5 21:34
 */

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

@WebServlet("/ser005")
public class servlet05 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {

        /*接收参数*/
        String uname=req.getParameter("uname");
        System.out.println("ser005 "+uname);/*接收不到*/

        System.out.println("servlet005");
    }
}
```

![image-20230205225123865](https://cdn.jsdelivr.net/gh/yzk656/image/202302052251921.png)

![image-20230205230013572](https://cdn.jsdelivr.net/gh/yzk656/image/202302052300607.png)

总结：重定向可以跨域，请求转发不能。

​			请求转发只能访问当前项目下的资源

## 2023-02-06

![image-20230206092233007](https://cdn.jsdelivr.net/gh/yzk656/image/202302060922082.png)

![image-20230206115346097](https://cdn.jsdelivr.net/gh/yzk656/image/202302061153188.png)

```java
package com.yzk.servlet;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.Cookie;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * @ClassName: cookie01
 * @Description: TODO
 * @Author: 杨振坤
 * @date: 2023/2/6 11:56
 */

@WebServlet("/cook01")
public class cookie01 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*Cookie的创建*/
        Cookie cookie=new Cookie("name","admin");
        /*发送（响应）Cookie*/
        resp.addCookie(cookie);
    }
}
```

![image-20230206120654375](https://cdn.jsdelivr.net/gh/yzk656/image/202302061215039.png)

```java
package com.yzk.servlet;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.Cookie;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * @ClassName: cookie01
 * @Description: TODO
 * @Author: 杨振坤
 * @date: 2023/2/6 11:56
 */

/**
 * cookie 的获取
 * 返回的是数组
 */
@WebServlet("/cook02")
public class cookie02 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        Cookie[] cookies = req.getCookies();
        /*判断cookie是否为空*/
        if (cookies != null && cookies.length > 0) {
            for(Cookie cookie:cookies){
                /*获取cookie的名称和值*/
                String name=cookie.getName();
                String value=cookie.getValue();
                System.out.println(name+" "+value);
            }
        }
    }
}

```

注意：cookie里面的内容是放在浏览器里面的，和你服务器是否关闭没有关系【默认是关闭浏览器后失效】

![image-20230206122048939](https://cdn.jsdelivr.net/gh/yzk656/image/202302061220010.png)

不同域名是无法*共享*浏览器端本地信息，包括*cookies*

```java
package com.yzk.servlet;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.Cookie;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * @ClassName: cookie01
 * @Description: cookie到期时间
 * @Author: 杨振坤
 * @date: 2023/2/6 11:56
 */

/**
 * cookie 的获取
 * 返回的是数组
 */
@WebServlet("/cook03")
public class cookie03 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        Cookie cookie=new Cookie("name","admin");
        cookie.setMaxAge(-1);
        resp.addCookie(cookie);

        Cookie cookie2=new Cookie("name1","admin1");
        cookie2.setMaxAge(30);
        resp.addCookie(cookie2);

        Cookie cookie3=new Cookie("name3","admin3");
        cookie3.setMaxAge(0);
        resp.addCookie(cookie3);
    }
}
```

![image-20230206160240314](https://cdn.jsdelivr.net/gh/yzk656/image/202302061602394.png)

![image-20230206160410416](https://cdn.jsdelivr.net/gh/yzk656/image/202302061604457.png)

```java
package com.yzk.servlet;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.Cookie;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;
import java.net.URLDecoder;
import java.net.URLEncoder;

/**
 * @ClassName: cookie01
 * @Description: cookie注意点
 * @Author: 杨振坤
 * @date: 2023/2/6 11:56
 */

/**
 * 大小有限，4kb左右
 */
@WebServlet("/cook04")
public class cookie04 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*cookie不能存中文，非要存的话，需要进行转化*/
        String name="姓名";
        String value="张三";

        name=URLEncoder.encode(name);
        value=URLEncoder.encode(value);

        Cookie cookie = new Cookie(name,value);
        resp.addCookie(cookie);

        Cookie[] cookies = req.getCookies();
        if (cookies != null) {
            for (Cookie cookie1 : cookies) {
                /*解码*/
                System.out.println(URLDecoder.decode(cookie1.getName()));
                System.out.println(URLDecoder.decode(cookie1.getValue()));
            }
        }

        /*出现同名cookie对象，则会进行覆盖*/
        Cookie cookie1=new Cookie("name","zhangsan");
        resp.addCookie(cookie1);
    }
}
```

![image-20230206184538869](https://cdn.jsdelivr.net/gh/yzk656/image/202302061845962.png)

![image-20230206184756251](https://cdn.jsdelivr.net/gh/yzk656/image/202302061847304.png)

![image-20230206191144226](https://cdn.jsdelivr.net/gh/yzk656/image/202302061911270.png)

![image-20230206191354540](https://cdn.jsdelivr.net/gh/yzk656/image/202302061913615.png)

![image-20230206211415421](https://cdn.jsdelivr.net/gh/yzk656/image/202302062114469.png)

```java
package com.yzk.session;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import jakarta.servlet.http.HttpSession;

import java.io.IOException;

/**
 * @ClassName: Session01
 * @Description: Session对象
 * @Author: 杨振坤
 * @date: 2023/2/6 21:05
 */
@WebServlet("/ss01")
public class Session01 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*获取Session对象*/
        HttpSession session = req.getSession();

        /*获取Session的对话标识符*/
        String id = session.getId();
        System.out.println(id);
        /*获取Session的创建时间*/
        System.out.println(session.getCreationTime());
        /*获取最后一次访问时间*/
        System.out.println(session.getLastAccessedTime());
        /*判断是否是新的session对象*/
        System.out.println(session.isNew());
    }
}
```

![image-20230206211436504](https://cdn.jsdelivr.net/gh/yzk656/image/202302062114573.png)

![image-20230206212221077](https://cdn.jsdelivr.net/gh/yzk656/image/202302062122140.png)

```java
package com.yzk.session;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import jakarta.servlet.http.HttpSession;

import java.io.IOException;

/**
 * @ClassName: Session01
 * @Description: Session域对象
 * @Author: 杨振坤
 * @date: 2023/2/6 21:05
 */

/**
 * 请求转发只使用 1 次请求，可以保留数据，因此使用请求转发方法
 * 请求转发
 *      一次请求
 *      request作用域有效
 *      Session作用域有效
 * 重定向
 *      两次请求
 *      request作用域无效
 *      Session作用域有效
 */
@WebServlet("/ss02")
public class Session02 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*获取Session对象*/
        HttpSession session = req.getSession();

        /*设置Session域对象*/
        session.setAttribute("uname", "admin");
        session.setAttribute("upwd", "123456");

        /*移除Session域对象*/
        session.removeAttribute("upwd");

        /*request域对象*/
        req.setAttribute("name", "zhangsan");
        req.setAttribute("pwd", "123");


        /*请求转发*/
//        req.getRequestDispatcher("index.jsp").forward(req, resp);

        /*重定向跳转*/
        resp.sendRedirect("index.jsp");
    }
}
```

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>$Title$</title>
</head>
<body>
<%
    /*获取Session域对象*/
    String uname = (String) request.getSession().getAttribute("uname");
    String upwd = (String) request.getSession().getAttribute("upwd");

    /*获取request域对象*/
    String name = (String) request.getAttribute("name");
    String pwd = (String) request.getAttribute("pwd");

    out.print(uname+" "+upwd);
    out.print(name+" "+pwd);
%>
</body>
</html>
```

![image-20230206214540163](https://cdn.jsdelivr.net/gh/yzk656/image/202302062145220.png)

![image-20230206224057399](https://cdn.jsdelivr.net/gh/yzk656/image/202302062240457.png)

![image-20230206224613337](https://cdn.jsdelivr.net/gh/yzk656/image/202302062246382.png)

![image-20230206224915397](https://cdn.jsdelivr.net/gh/yzk656/image/202302062249443.png)

![image-20230206225022592](https://cdn.jsdelivr.net/gh/yzk656/image/202302062250638.png)

## 2023-02-07

![image-20230207171535157](https://cdn.jsdelivr.net/gh/yzk656/image/202302071715264.png)

![image-20230207173023875](https://cdn.jsdelivr.net/gh/yzk656/image/202302071730940.png)

```java
package com.yzk.ServletContext;

import jakarta.servlet.ServletContext;
import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * @ClassName: Servlet01
 * @Description: TODO
 * @Author: 杨振坤
 * @date: 2023/2/7 17:30
 */

@WebServlet("/servletContext01")
public class Servlet01 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*通过Request对象获取*/
        ServletContext servletContext = req.getServletContext();

        /*通过Session对象获取*/
        ServletContext servletContext1 = req.getSession().getServletContext();

        /*通过ServletConfig对象获取*/
        ServletContext servletContext2 = getServletConfig().getServletContext();

        /*直接获取*/
        ServletContext servletContext3 = getServletContext();

        /*常用方法*/
        /*1、获取当前服务器的版本信息*/
        String serverInfo = req.getServletContext().getServerInfo();
        System.out.println(serverInfo);
        /*2、获取项目的真实路径*/
        String realPath = req.getServletContext().getRealPath("/");
        System.out.println(realPath);
    }
}

```

![image-20230207174952355](https://cdn.jsdelivr.net/gh/yzk656/image/202302071749428.png)

![image-20230207202623466](https://cdn.jsdelivr.net/gh/yzk656/image/202302072026562.png)

![image-20230207204938244](https://cdn.jsdelivr.net/gh/yzk656/image/202302072049316.png)

![image-20230207205149182](https://cdn.jsdelivr.net/gh/yzk656/image/202302072051275.png)

```java
package com.yzk.UploadServlet;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.MultipartConfig;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import jakarta.servlet.http.Part;

import java.io.IOException;

/**
 * @ClassName: UploadServlet
 * @Description: 文件上传
 * @Author: 杨振坤
 * @date: 2023/2/7 20:53
 */

@WebServlet("/UploadServlet")
/**
 *如果是文件上传，一定要加该注解
 */
@MultipartConfig
public class UploadServlet extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("文件上传。。。");
        /*设置请求的编码格式*/
        req.setCharacterEncoding("UTF-8");

        /*获取普通表项（获取参数）*/
        String uname = req.getParameter("uname");
        System.out.println(uname);
        /*获取Part对象（Servlet将multipart/form-data的Post请求封装成Part对象）*/
        Part part = req.getPart("my_file");
        /*通过Part对象得到上传的文件名*/
        String filename = part.getSubmittedFileName();
        System.out.println(filename);
        /*得到文件的存放路径*/
        String filepath = req.getServletContext().getRealPath("/");
        System.out.println("文件的存放路径:"+filepath);
        /*上传文件到指定目录*/
        part.write(filepath + "/" + filename);
    }
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>文件上传</title>
</head>
<body>
<!--文件上传
    1. 准备表单
    2. 设置表单提交类型为Post请求 method=“post”
    3. 设置表单为文件上传地址 enctype="multipart/form-data"
    4. 设置文件提交地址
    5. 准备表单元素
        1. 普通表单项 type=“text”；
        2. 文件项 type=“file”
    6. 设置表单元素的name值（表单提交一定要设置表单元素的name属性值，否则后台无法接收数据）
-->

<form action="UploadServlet" method="post" enctype="multipart/form-data">
    姓名：<input type="text" name="uname"><br>
    文件：<input type="file" name="my_file"><br>
    <!--button默认类型是提交表单，type=submit-->
    <button>提交</button>
</form>
</body>
</html>
```

![image-20230207222104010](https://cdn.jsdelivr.net/gh/yzk656/image/202302072221089.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>文件下载</title>
</head>
<body>
<!--
    超链接下载
        当使用超链接时，如果遇到浏览器能够识别的资源，则会显示内容
        如果遇到浏览器不能识别的资源，则会进行下载
    download属性
        通过download属性规定浏览器进行下载
-->

<!--浏览器能够识别的资源-->
<a href="download/新建文本文档.txt">文本文件</a>
<a href="download/复杂度.png">图片文件</a>
<!--浏览器不能识别的资源-->
<a href="download/《TCP-IP详解卷1：协议》.zip">压缩文件</a>
<hr>
<a href="download/新建文本文档.txt"download="">文本文件</a>
<a href="download/复杂度.png" download="百度.png">图片文件</a>

</body>
</html>
```

==注意：==浏览器要想访问项目内的文件夹，需要在进行部署【不加/sc04也得到正常的结果】

![image-20230207230857309](https://cdn.jsdelivr.net/gh/yzk656/image/202302072308354.png)

![image-20230207231233733](https://cdn.jsdelivr.net/gh/yzk656/image/202302072312823.png)

![image-20230207231831419](https://cdn.jsdelivr.net/gh/yzk656/image/202302072318497.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>文件下载</title>
</head>
<body>
<!--
    超链接下载
        当使用超链接时，如果遇到浏览器能够识别的资源，则会显示内容
        如果遇到浏览器不能识别的资源，则会进行下载
    download属性
        通过download属性规定浏览器进行下载
-->

<!--浏览器能够识别的资源-->
<a href="download/新建文本文档.txt">文本文件</a>
<a href="download/复杂度.png">图片文件</a>
<!--浏览器不能识别的资源-->
<a href="download/《TCP-IP详解卷1：协议》.zip">压缩文件</a>
<hr>
<a href="download/新建文本文档.txt"download="">文本文件</a>
<a href="download/复杂度.png" download="百度.png">图片文件</a>

<hr>
<form action="downloadServlet2">
    文件名：<input type="text" name="filename" placeholder="请输入要下载的文件名">
    <button>下载</button>
</form>

</body>
</html>
```

```java
package com.yzk.UploadServlet;

import jakarta.servlet.Servlet;
import jakarta.servlet.ServletException;
import jakarta.servlet.ServletOutputStream;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStream;

/**
 * @ClassName: DownloadServlet2
 * @Description: TODO
 * @Author: 杨振坤
 * @date: 2023/2/7 23:23
 */
@WebServlet("/downloadServlet2")
public class DownloadServlet2 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("文件正在下载");

        /*设置请求的编码格式*/
        req.setCharacterEncoding("UTF-8");
        resp.setContentType("text/html;charset=UTF-8");
        /*获取参数（得到要下载的名字）*/
        String filename = req.getParameter("filename");
        /*参数的非空判断*/
        if (filename == null || filename.trim().equals("")) {
            resp.getWriter().write("请输入要下载的文件名");
            resp.getWriter().close();
            return;
        }

        /*得到图片存放的路径*/
        String path = req.getServletContext().getRealPath("/download/");
        /*通过路径得到file路径*/
        File file = new File(path + filename);
        /*判断文件对象是否存在并且是否是一个标准文件*/
        if (file.exists() && file.isFile()) {
            /*设置响应类型（浏览器无法使用某种方式或者激活某个程序来处理的 MIME 类型）*/
            resp.setContentType("application/x-msdownload");
            /*设置响应头*/
            resp.setHeader("Content-Disposition", "attachment;filename=" + filename);
            /*得到文件的输入流*/
            InputStream in = new FileInputStream(file);
            /*得到字节输出流*/
            ServletOutputStream out = resp.getOutputStream();
            /*定义byte数组*/
            byte[] bytes = new byte[1024];
            /*定义长度*/
            int len = 0;
            /*循环输出*/
            while ((len = in.read()) != -1) {
                /*输出*/
                out.write(bytes,0,len);
            }
            /*关闭资源*/
            out.close();
            in.close();
        } else {
            resp.getWriter().write("文件不存在，请重试！！！");
            resp.getWriter().close();
            return;
        }
    }
}
```

# JSP

## 2022-02-08

![image-20230208130023014](https://cdn.jsdelivr.net/gh/yzk656/image/202302081300115.png)

![image-20230208130419061](https://cdn.jsdelivr.net/gh/yzk656/image/202302081304138.png)

![image-20230208130638735](https://cdn.jsdelivr.net/gh/yzk656/image/202302081306792.png)

![image-20230208133159153](https://cdn.jsdelivr.net/gh/yzk656/image/202302081331221.png)

![image-20230208134814458](https://cdn.jsdelivr.net/gh/yzk656/image/202302081348513.png)

![image-20230208192240471](https://cdn.jsdelivr.net/gh/yzk656/image/202302081922557.png)

```java
<%--
  Created by IntelliJ IDEA.
  User: 27939
  Date: 2023/2/8
  Time: 19:24
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>脚本小程序</title>
</head>
<body>
<%--第一种：Java代码，可以写Java代码，定义局部变量。编写语句--%>
<%
    String str="111";
    System.out.println(str);
    out.write(str);

    /*输出全局变量*/
    out.write("全局变量："+num);
%>
<%--第二种：生命区局变量、方法、类等--%>
<%!
    int num=10;
%>
<%--第三种：输出表达式，可以输出变量或字面量--%>
<%=
    str
%>

</body>
</html>
```

![image-20230208205427210](https://cdn.jsdelivr.net/gh/yzk656/image/202302082054282.png)

![image-20230208205721630](https://cdn.jsdelivr.net/gh/yzk656/image/202302082057696.png)

![image-20230208224233268](https://cdn.jsdelivr.net/gh/yzk656/image/202302082242450.png)

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 27939
  Date: 2023/2/8
  Time: 21:00
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>include静态包含</title>
</head>
<body>

<%@include file="04-header.jsp" %>
<h2>主题内容</h2>
<%@include file="04-footer.jsp" %>

</body>
</html>

```

```java
<%--
  Created by IntelliJ IDEA.
  User: 27939
  Date: 2023/2/8
  Time: 21:00
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>底部信息</title>
</head>
<body>
<h2>底部内容</h2>
</body>
</html>
```

```java
<%--
  Created by IntelliJ IDEA.
  User: 27939
  Date: 2023/2/8
  Time: 21:00
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>头部信息</title>
</head>
<body>

<h2>头部内容</h2>

</body>
</html>
```

![image-20230208224355262](https://cdn.jsdelivr.net/gh/yzk656/image/202302082243316.png)

![image-20230208225418830](https://cdn.jsdelivr.net/gh/yzk656/image/202302082254878.png)

![image-20230208230302030](https://cdn.jsdelivr.net/gh/yzk656/image/202302082303074.png)

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 27939
  Date: 2023/2/8
  Time: 22:44
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>include动态包含</title>
</head>
<body>
<%--相当于方法的调用
        可以有同名变量
        jsp标签中间是添加参数的，如果不添加参数，空格都不能添加
--%>

<%
    int a = 1;
%>
<%
    String str = "123456";
    String url = "04-footer.jsp";
%>


<jsp:include page="04-header.jsp"></jsp:include>
<h2>主题内容</h2>
<%--注意：注释两旁的也算空格，因此jsp标签里面不能写注释
    page也能通过变量定义
--%>
<jsp:include page="<%=url%>">
    <jsp:param name="uname" value="admin"></jsp:param>
    <jsp:param name="upwd" value="<%=str%>"></jsp:param>
</jsp:include>
</body>
</html>
```

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 27939
  Date: 2023/2/8
  Time: 21:00
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>底部信息</title>
</head>
<body>
<h2>底部内容</h2>

<%--获取参数--%>
<%
    int a = 10;
    String uname = request.getParameter("uname");
    String pwd = request.getParameter("upwd");
    out.print(uname + " " + pwd);
%>

</body>
</html>
```

![image-20230208231306244](https://cdn.jsdelivr.net/gh/yzk656/image/202302082313313.png)

![image-20230208232029337](https://cdn.jsdelivr.net/gh/yzk656/image/202302082320394.png)



![image-20230208233719532](https://cdn.jsdelivr.net/gh/yzk656/image/202302082337577.png)

![image-20230208233701343](https://cdn.jsdelivr.net/gh/yzk656/image/202302082337395.png)

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/8
  Time: 23:23
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%
    /*设置Page范围内的域对象*/
    pageContext.setAttribute("name1","zhangsan");

    /*设置request范围内的域对象*/
    request.setAttribute("name2","lisi");

    /*设置session范围内的域对象*/
    session.setAttribute("name3","yzk");

    /*设置application范围内的域对象*/
    application.setAttribute("name4","zhaosi");

%>


<%--    /*jsp中服务端跳转*/--%>
<%--<jsp:forward page="06-JSP的四大域对象02.jsp"></jsp:forward>--%>

    <%--服务端跳转是通过超链接实现--%>
<a href="06-JSP的四大域对象02.jsp">跳转</a>
</body>
</html>
```

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/8
  Time: 23:23
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%
    /*获取域对象的值*/
    /*page范围*/
    out.print("page范围" + pageContext.getAttribute("name1")+"<br>");
    out.print("request范围" + request.getAttribute("name2")+"<br>");
    out.print("session范围" + session.getAttribute("name3")+"<br>");
    out.print("application范围" + application.getAttribute("name4")+"<br>");
%>
</body>
</html>
```

## 2023-02-09

简单的登录功能

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/9
  Time: 21:15
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<form action="login_servlet" method="post">
    姓名：<input type="text" name="uname"><br>
    密码：<input type="password" name="upwd"><br>
    <button>登录</button>
    <span style="color: red;font-size: 12px"><%=request.getAttribute("msg")%></span>
</form>
</body>
</html>
```

```java
package com.yzk.controller;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

/**
 * @ClassName: Login_servlet
 * @Description: TODO
 * @Author: 杨振坤
 * @date: 2023/2/9 21:18
 */

@WebServlet("/login_servlet")
public class LoginServlet extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*设置客户端的编码格式*/
        req.setCharacterEncoding("UTF-8");

        /*接收客户端传递的参数*/
        String uname = req.getParameter("uname");
        String upwd = req.getParameter("upwd");

        /*判断参数是否为空*/
        if (uname == null || uname.trim().equals("")) {
            req.setAttribute("msg", "用户姓名不能为空");
            req.getRequestDispatcher("login.jsp").forward(req, resp);
            return;
        }
        if (upwd == null || upwd.trim().equals("")) {
            req.setAttribute("msg", "用户密码不能为空");
            req.getRequestDispatcher("login.jsp").forward(req, resp);
            return;
        }

        /*判断账号，密码是否正确*/
        if (!uname.equals("admin") || !upwd.equals("admin")) {
            req.setAttribute("msg","登录失败");
            req.getRequestDispatcher("login.jsp").forward(req,resp);
            return;
        }

        /*登录成功*/
        /*设置登录信息到Session作用域*/
        req.getSession().setAttribute("uname",uname);
        resp.sendRedirect("index.jsp");
    }
}
```

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>$Title$</title>
</head>
<body>
    <h2>欢迎<%=session.getAttribute("uname")%>登录</h2>
</body>
</html>
```

![image-20230209214406139](https://cdn.jsdelivr.net/gh/yzk656/image/202302092144282.png)

解决显示`null`值的情况

![image-20230209220910370](https://cdn.jsdelivr.net/gh/yzk656/image/202302092209418.png)

![image-20230209221036011](https://cdn.jsdelivr.net/gh/yzk656/image/202302092210060.png)

```jsp
<%@ page import="com.yzk.session.Session01" %><%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/9
  Time: 22:17
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%--
    EL表达式一般操作的是域对象，不能操作局部变量
    EL表达式获取对象的值为空，默认显示空字符串
    EL表达式默认从小到大范围去找，找到即可，如果四个对象（page、request、session、application）都没找到，就显示空字符串
    获取指定范围内的域对象：<br>
        ${sessionScope.uname}
--%>
<%
    pageContext.setAttribute("uname","yzk1");
    request.setAttribute("uname","yzk2");
    session.setAttribute("uname","yzk3");
    application.setAttribute("uname","yzk4");

    /*定义局部变量*/
    String str="123";
%>

<%--获取数据--%>
获取局部变量：${str}<br>
获取域对象：${uname}<br>

获取指定范围内的域对象：<br>
${sessionScope.uname}


</body>
</html>

```

![image-20230209222929119](https://cdn.jsdelivr.net/gh/yzk656/image/202302092229163.png)

![image-20230209223204898](https://cdn.jsdelivr.net/gh/yzk656/image/202302092232972.png)

![image-20230209223220284](https://cdn.jsdelivr.net/gh/yzk656/image/202302092232356.png)

![image-20230209223254503](https://cdn.jsdelivr.net/gh/yzk656/image/202302092232545.png)

![image-20230209223311810](https://cdn.jsdelivr.net/gh/yzk656/image/202302092233862.png)

![image-20230209223323322](https://cdn.jsdelivr.net/gh/yzk656/image/202302092233375.png)

![image-20230210003722433](https://cdn.jsdelivr.net/gh/yzk656/image/202302100037523.png)

```jsp
<%@ page import="java.util.List" %>
<%@ page import="java.util.ArrayList" %>
<%@ page import="java.util.Map" %>
<%@ page import="java.util.HashMap" %>
<%@ page import="com.yzk.po.User" %><%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/9
  Time: 22:48
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%
    /*list*/
    List<String> list=new ArrayList<>();
    list.add("aaa");
    list.add("bbb");
    list.add("ccc");
    request.setAttribute("list",list);

    /*map*/
    Map map=new HashMap();
    map.put("aaa","1111");
    map.put("bbb","2222");
    map.put("ccc","3333");
    request.setAttribute("map",map);

    /*JavaBean*/
    User user=new User();
    user.setUser_id(1);
    user.setUname("yzk");
    user.setUpwd("123456");
    request.setAttribute("user",user);

%>

获取list
${list.size()}<br>
${list.get(1)};<br>

获取Map
${map.aaa}<br>
${map["aaa"]}<br>

获取JavaBean
${user.uname}<br>
${user.getUname()}

</body>
</html>

```

```java
package com.yzk.po;

/**
 * @ClassName: User
 * @Description: TODO
 * @Author: 杨振坤
 * @date: 2023/2/10 0:27
 */
public class User {
    private Integer user_id;
    private String uname;
    private String upwd;

    public User() {
    }

    public User(Integer user_id, String uname, String upwd) {
        this.user_id = user_id;
        this.uname = uname;
        this.upwd = upwd;
    }

    public Integer getUser_id() {
        return user_id;
    }

    public void setUser_id(Integer user_id) {
        this.user_id = user_id;
    }

    public String getUname() {
        return uname;
    }

    public void setUname(String uname) {
        this.uname = uname;
    }

    public String getUpwd() {
        return upwd;
    }

    public void setUpwd(String upwd) {
        this.upwd = upwd;
    }
}

```

## 2023-02-10

![image-20230210094909728](https://cdn.jsdelivr.net/gh/yzk656/image/202302100949797.png)

![image-20230210101832778](https://cdn.jsdelivr.net/gh/yzk656/image/202302101018854.png)

![image-20230210101913154](https://cdn.jsdelivr.net/gh/yzk656/image/202302101019219.png)

![image-20230210101934327](https://cdn.jsdelivr.net/gh/yzk656/image/202302101019383.png)

```jsp
<%@ page import="java.util.List" %>
<%@ page import="java.util.ArrayList" %>
<%@ page import="java.util.HashMap" %>
<%@ page import="java.util.Map" %>
<%@ page import="com.yzk.po.User" %><%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/10
  Time: 9:58
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%--
    对于字符串、List、Map空对象看为null
    对于JavaBean 空构造函数不算null
--%>
<%
    /*字符串*/
    request.setAttribute("str1","aaa");
    request.setAttribute("str2","");
    request.setAttribute("str3",null);

    /*List*/
    List list1=new ArrayList();
    List list2=null;
    List list3=new ArrayList();
    list1.add(1);
    request.setAttribute("list1",list1);
    request.setAttribute("list2",list2);
    request.setAttribute("list3",list3);

    /*Map*/
    Map map1=null;
    Map map2=new HashMap();
    Map map3=new HashMap();
    map3.put(1,2);
    request.setAttribute("map1",map1);
    request.setAttribute("map2",map2);
    request.setAttribute("map3",map3);

    /*JavaBean*/
    User user1=null;
    User user2=new User();
    User user3=new User();
    user3.setUser_id(1);
    request.setAttribute("user1",user1);
    request.setAttribute("user2",user2);
    request.setAttribute("user3",user3);
%>
字符串 <br>
${empty str}<br>
${empty str1}<br>
${empty str2}<br>
${empty str3}<br>

<hr>

List <br>
${empty list1}<br>
${empty list2}<br>
${empty list3}<br>

<hr>

Map <br>
${empty map1}<br>
${empty map2}<br>
${empty map3}<br>

<hr>

JavaBean <br>
${empty user1}<br>
${empty user2}<br>
${empty user3}<br>

</body>
</html>
```

# JSTL

## 2023-02-10

![image-20230210102209396](https://cdn.jsdelivr.net/gh/yzk656/image/202302101022466.png)

![image-20230210102841831](https://cdn.jsdelivr.net/gh/yzk656/image/202302101028892.png)

==注意==：在运行JSTL时，报错

```jsp
org.apache.jasper.JasperException: java.lang.ClassNotFoundException: org.apache.jsp._01_002dJSTL的使用_jsp
```

https://blog.csdn.net/qq_27130163/article/details/115665919

![image-20230210212410848](https://cdn.jsdelivr.net/gh/yzk656/image/202302102124928.png)

![image-20230210212423280](https://cdn.jsdelivr.net/gh/yzk656/image/202302102124315.png)

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/10
  Time: 10:34
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%--通过 taglib 标签引入所需要的标签库--%>
<%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%--
    JSTL的使用
        1. 下载JSTL所需要的jar包（standaard.jar 和 jstl.jar）
        2. 在项目的web目录下的web—INF中新建lib目录，将jar包拷贝进去
        3. 选择目录结构 ，将jar包添加为依赖，
--%>
<c:if test="${1==1}">
    Hello JSTL
</c:if>
</body>
</html>
```

![image-20230210212523614](https://cdn.jsdelivr.net/gh/yzk656/image/202302102125698.png)

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/10
  Time: 22:42
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%--
    常用属性
        test：操作的是域对象，接收返回结果是boolean类型的值(必要属性)
        var：限域变量名（存放在作用域的变量名），用来接收判断结果的值（可选属性）
        scope：限域变量名的范围(page\request\session\application)（可选属性）

        获取结果时 超过指定范围，就获取不到了
--%>
<%
    /*设置数据*/
    request.setAttribute("num", 10);
%>

<c:if test="${num>0}">
    数值大于0
</c:if>

<c:if test="${num>100}" var="flag" scope="request">
</c:if>
${flag}---${sessionScope.flag}--${requestScope.flag}

</body>
</html>
```

![image-20230211002827123](https://cdn.jsdelivr.net/gh/yzk656/image/202302110028193.png)

![image-20230211003725293](https://cdn.jsdelivr.net/gh/yzk656/image/202302110037351.png)

![image-20230211003834679](https://cdn.jsdelivr.net/gh/yzk656/image/202302110038738.png)

![image-20230211004055981](https://cdn.jsdelivr.net/gh/yzk656/image/202302110040028.png)

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/11
  Time: 0:29
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>

<%
    request.setAttribute("score",80);
%>

<c:choose>
    <c:when test="${score<60}">
        小渣渣
    </c:when>
    <c:when test="${score==60}">
        及格
    </c:when>
    <c:when test="${score>60&&score<=80}">
        良好
    </c:when>
    <c:otherwise>
        大神
    </c:otherwise>
</c:choose>

</body>
</html>
```

![image-20230211004225784](https://cdn.jsdelivr.net/gh/yzk656/image/202302110042859.png)

![](https://cdn.jsdelivr.net/gh/yzk656/image/202302110043065.png)

![](https://cdn.jsdelivr.net/gh/yzk656/image/202302110043288.png)

```jsp
<%@ page import="java.util.List" %>
<%@ page import="java.util.ArrayList" %><%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/11
  Time: 0:48
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<c:forEach var="i" begin="1" end="10" step="2">
    ${i}
</c:forEach>

<%
    List<String> list=new ArrayList<>();
    for(int i=1;i<=10;i++){
        list.add("A:"+i);
    }
    pageContext.setAttribute("list",list);
%>

<c:forEach items="${list}" var="i">
    ${i}
</c:forEach>
</body>
</html>
```

![image-20230211010858010](https://cdn.jsdelivr.net/gh/yzk656/image/202302110108090.png)

![image-20230211010934559](https://cdn.jsdelivr.net/gh/yzk656/image/202302110109613.png)

![image-20230211013429417](https://cdn.jsdelivr.net/gh/yzk656/image/202302110134487.png)

![image-20230211013654545](https://cdn.jsdelivr.net/gh/yzk656/image/202302110136623.png)

```jsp
<%--
  Created by IntelliJ IDEA.
  User: 杨振坤
  Date: 2023/2/11
  Time: 1:37
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%--
    如果只是用于一次输出，则不用设置var属性，他会自动输出
    但是如果设置了value属性，想要获取值，就必须使用var属性
    默认类型是Number
--%>


<fmt:formatNumber value="10" type="number" var="num"></fmt:formatNumber>
${num}
<fmt:formatNumber value="10" type="percent"></fmt:formatNumber>
<fmt:formatNumber value="10" type="currency"></fmt:formatNumber>

<%--设置时区--%>
<fmt:setLocale value="en_US"></fmt:setLocale>
<fmt:formatNumber value="10" type="currency"></fmt:formatNumber>


</body>
</html>
```

![image-20230211014946108](https://cdn.jsdelivr.net/gh/yzk656/image/202302110149184.png)

![image-20230211020036853](https://cdn.jsdelivr.net/gh/yzk656/image/202302110200943.png)

```jsp
<%--格式化日期--%>
<%
    request.setAttribute("my_date",new Date());
%>
<fmt:formatDate value="${my_date}"/> <br>
<fmt:formatDate value="${my_date}" type="date"/><br>
<fmt:formatDate value="${my_date}" type="time"/><br>
<fmt:formatDate value="${my_date}" type="both"/><br>
<fmt:formatDate value="${my_date}" type="both" dateStyle="full"/><br>
<fmt:formatDate value="${my_date}" type="both" dateStyle="short"/><br>
<fmt:formatDate value="${my_date}" pattern="yyyy-MM-dd"/><br>
```

![image-20230211020204665](https://cdn.jsdelivr.net/gh/yzk656/image/202302110202740.png)

![image-20230211021000738](https://cdn.jsdelivr.net/gh/yzk656/image/202302110210787.png)

![image-20230211021338735](https://cdn.jsdelivr.net/gh/yzk656/image/202302110213812.png)

```jsp
<%--<fmt:setLocale value="zh_CN"/>--%>
<fmt:parseNumber value="100"/><br>
<fmt:parseNumber value="100" type="number"/><br>
<fmt:parseNumber value="100%" type="percent"/><br>
<fmt:parseNumber value="$100.00" type="currency"/><br>

下面这个注释为解决，上面那个使用中文￥也未解决
<%--<fmt:parseDate value="2:21:10 AM" type="date"/><br>--%>
<fmt:parseDate value="2020/01/16" pattern="yyyy/MM/dd"/><br>
```

## 2023-02-12

![image-20230212110949579](https://cdn.jsdelivr.net/gh/yzk656/image/202302121109679.png)
