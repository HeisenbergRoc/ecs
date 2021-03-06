# ModifyImageAttribute {#doc_api_999579 .reference}

修改一份自定义镜像的名称和描述。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Ecs&api=ModifyImageAttribute)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ImageId|String|是|m-imageid1|自定义镜像的 ID。

 |
|RegionId|String|是|cn-hangzhou|自定义镜像所在的地域 ID。您可以调用 [DescribeRegions](~~25609~~) 查看最新的阿里云地域列表。

 |
|Action|String|否|ModifyImageAttribute|系统规定参数。取值：ModifyImageAttribute

 |
|Description|String|否|FinanceDept|自定义镜像的描述信息。

 -   能包含 0~256 个字符。
-   不能以 http:// 和 https:// 开头。
-   不填则为空，默认为空。

 |
|ImageName|String|否|FinanceJoshua|自定义镜像名称。

 -   能包含 2~128 个英文或中文字符。
-   必须以大小字母或中文开头，可包含数字、半角冒号（:）、下划线（\_）或者连字符（-）。
-   不能以 http:// 和 https:// 开头。

 |
|OwnerAccount|String|否|@Alibaba.com|RAM用户的账号登录名称。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E|请求 ID。无论调用接口成功与否，我们都会返回请求 ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ecs.aliyuncs.com/?Action=ModifyImageAttribute
&ImageId=m-imageid1
&RegionId=cn-hangzhou
&ImageName=FinanceJoshua
&Description=FinanceDept
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyImageAttributeResponse>
  <RequestId>C8B26B44-0189-443E-9816-D951F59623A9</RequestId>
</ModifyImageAttributeResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C8B26B44-0189-443E-9816-D951F59623A9"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The input parameter "RegionId" that is mandatory for processing this request is not supplied.|区域ID不得为空。|
|400|InvalidImageName.Duplicated|The specified Image name has already bean used.|镜像名称已经重复。|
|400|InvalidDescription.Malformed|The specified description is wrongly formed.|指定的资源描述格式不合法。长度为2-256个字符，不能以 http:// 和 https:// 开头。|
|404|InvalidImageId.NotFound|The specified ImageId does not exist.|指定的镜像在该用户账号下不存在，请您检查镜像id是否正确。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Ecs)

