# 接口文档的规范与写作

## 说明

*TODO*

## 参考文档

- github API
- [RESTful API 设计指南](http://www.ruanyifeng.com/blog/2014/05/restful_api.html)

## ChangLog

- 2014/9/25
    - create

## 目录

*TODO*

## 正文

前后端在业务上进行合作的时候， **接口** 将会成为其合作桥梁。那么如何编写风格良好的合作文档呢？此文将会阐述接口文档编写的一些方面及注意事项。

从宏观上，接口可分为 **异步接口** 和 **同步接口** 两类，

- 异步接口，其本质是 *ajax* 调用
- 同步接口，在web后端编译html模版返回给前端展示

### 1 异步接口文档编写规范

异步接口的文档规范包含如下几个方面，

- 接口命名
- 接口参数
- 接口返回值
- ...

#### 1.1 接口命名

推荐使用 *[驼峰式](http://zh.wikipedia.org/wiki/%E9%A7%9D%E5%B3%B0%E5%BC%8F%E5%A4%A7%E5%B0%8F%E5%AF%AB)* 的 **动宾结构的短语** 来表示，比如，

- `getMessageList`
- `getUserInfo`
- ...

唯一的原则就是 **见名知意** 。

#### 1.2 接口参数及返回值

接口的参数及返回值一般跟具体的业务强关联，下面给出一个示例，

----------

### 1 detectCDN&url={url}

- Tags
 
    **async** **get**

- Description

    探测某一url是否使用了cdn服务。

- Changelog

    - 2014/9/9
        - 创建
    - 2014/9/10
        - 更新返回值说明

- Parameters

    ```javascript
    {
        "url": "www.baidu.com"
    }
    ```

    **说明**，
    1. `url`: **`String`** 标识需要探测的url地址，url可以不用带协议

- Method

    **GET**

- Return

    ```javascript
    {
        "code": 200,
        "message": "detect cdn successfully.",
        "data": {
            "cdn_used": true,
            "cdn_provider": "xxx",
            "dns_provider": "xxx"
        }
    }
    ```

    **说明** ，
    1. `data.cdn_used`: **`Boolean`** 表示特定url是否使用了相关cdn服务
    2. `data.cdn_provider`: **`String`** cdn服务商名称
    3. `data.dns_provider`: **`String`** dns服务商名称

----------

从上面的例子中可以看出，一份良好的借口文档应该明确包含如下的信息，

- Tags，标识接口的分类标签信息，比如是否是异步接口，使用何种http谓语等
- Description，给出接口的描述信息，指明此接口的左右
- Changelog，给出接口的更新日志，有助于沉淀接口的版本演化信息
- Parameters，对接口的参数进行说明。一般此项还会附带 **额外的说明信息** ，比如说明参数的数据类型等
- Method，接口使用哪种http方法
- Return，接口的返回值。此项一般也会带有 **额外的说明信息**，比如明确参数的数据类型、部分业务信息的说明等

完成接口文档之后，前后端即可开始各自的开发，只要遵循此接口文档即可。

#### 1.3 返回值的一般规范

为了对接口返回值进行统一的业务逻辑判断，我们会有一个一般性的规范对接口返回值进行规范。

返回值一般包含如下几个域值，

- `code`: **Integer** 返回值状态码。不同的状态码通常具有不同的含义。
- `message`: **String** 返回值的一般性说明。
- `data`: 标识返回值的数据域，此域的类型是不固定的，通常为 **Object**

除了以上几个基本的域值之外，可能会根据具体的业务需求添加一些 **额外的数据域** ，此时前后端提前做好协调说明即可。

下面给出一份状态码的定义，

| code | sense | description |
| --- | --- | --- |
| 200 | Ok | The `GET`, `PUT`, `DELETE` request was successful, the resource(s) itself is returned as `JSON`. |
| 201 | Created | The `POST` request was successful and the resource is returned as `JSON`. |
| 400 | Bad Request | A required attribute of the API request is missing, e.g. the title of an isssue is not given. |
| 401 | Unanthorized | The user is not authenticated, a valid user token is necessary. |
| 403 | Forbidden | The request is not allowed, e.g. the user is not allowed to delete a project. |
| 404 | Not Found | A resource could not be accessed, e.g. an ID for a resource could not be found. |
| 405 | Method Not Allowed | The request is not supported. |
| 409 | Conflict | A conflicting reosurce already exists, e.g. creating a project with a name that already exists. |
| 500 | Server Error | While handing the request something wnet wrong on the server side. |

上述的定义参与自github的api文档，后面我们将会以此为基础，作相应的调整和补充。


### 2 同步接口文档编写规范

*TODO*

### 3 RESTful API设计

*TODO*

### 4 基于服务的前后端协作开发

*TODO*