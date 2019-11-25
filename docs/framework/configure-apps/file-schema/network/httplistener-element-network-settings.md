---
title: <httpListener> 元素（网络设置）
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088379"
---
# <a name="httplistener-element-network-settings"></a>\<httpListener > 元素（网络设置）
自定义 <xref:System.Net.HttpListener> 类使用的参数。  

[ **\<configuration>** ](../configuration-element.md)\
\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**设置 >** ](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpListener >**

## <a name="syntax"></a>语法  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>键入  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|unescapeRequestUrl|一个布尔值，该值指示 <xref:System.Net.HttpListener> 实例是否使用原始未转义 URI 而不是已转换的 URI。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**描述**|  
|-----------------|---------------------|  
|[设置](settings-element-network-settings.md)|配置 <xref:System.Net> 命名空间的基本网络选项。|  
  
## <a name="remarks"></a>备注  
 **UnescapeRequestUrl**特性指示 <xref:System.Net.HttpListener> 是否使用原始未转义 uri 而不是转换的 uri （其中任何百分比编码值都已转换）并执行其他规范化步骤。  
  
 当 <xref:System.Net.HttpListener> 实例通过 `http.sys` 服务收到请求时，它会创建 `http.sys`提供的 URI 字符串的实例，并将其公开为 <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> 属性。  
  
 `http.sys` 服务公开了两个请求 URI 字符串：  
  
- 原始 URI  
  
- 转换的 URI  
  
 原始 URI 是 HTTP 请求的请求行中提供的 <xref:System.Uri?displayProperty=nameWithType>：  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 `http.sys` 为上述请求提供的原始 URI 为 "/path/"。 这表示 HTTP 谓词后的字符串，因为它是通过网络发送的。  
  
 `http.sys` 服务通过使用 HTTP 请求行中提供的 URI 和主机标头确定请求应转发到的源服务器，从请求中提供的信息创建转换的 URI。 这是通过将请求中的信息与一组已注册的 URI 前缀进行比较来完成的。 HTTP 服务器 SDK 文档将此转换的 URI 称为 HTTP_COOKED_URL 结构。  
  
 为了能够将请求与已注册的 URI 前缀进行比较，需要对请求进行一些规范化。 对于上面的示例，转换后的 URI 如下所示：  
  
 `http://www.contoso.com/path/`  
  
 `http.sys` 服务将 <xref:System.Uri.Host%2A?displayProperty=nameWithType> 属性值与请求行中的字符串结合起来，以创建转换的 URI。 此外，`http.sys` 和 <xref:System.Uri?displayProperty=nameWithType> 类还会执行以下操作：  
  
- 取消转义所有百分比编码值。  
  
- 将百分号编码的非 ASCII 字符转换为 UTF-16 字符表示形式。 请注意，支持 UTF-8 和 ANSI/DBCS 字符以及 Unicode 字符（使用% uXXXX 格式的 Unicode 编码）。  
  
- 执行其他规范化步骤，如路径压缩。  
  
 由于请求不包含任何有关用于百分比编码值的编码的信息，因此只需分析百分比编码的值就不能确定正确的编码。  
  
 因此 `http.sys` 提供了两个注册表项用于修改进程：  
  
|注册表项|默认值|描述|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|如果为零，则 `http.sys` 仅接受 UTF-8 编码的 Url。<br /><br /> 如果非零，则 `http.sys` 还会接受请求中 ANSI 编码或 DBCS 编码的 Url。|  
|FavorUTF8|1|如果非零，则 `http.sys` 始终首先尝试将 URL 解码为 UTF-8;如果该转换失败并且 EnableNonUTF8 为非零，则 Http.sys 会尝试将其解码为 ANSI 或 DBCS。<br /><br /> 如果为零（并且 EnableNonUTF8 为非零），`http.sys` 将尝试将其解码为 ANSI 或 DBCS;如果未成功，则它将尝试 UTF-8 转换。|  
  
 <xref:System.Net.HttpListener> 收到请求时，它会将转换的 URI 从 `http.sys` 作为输入 <xref:System.Net.HttpListenerRequest.Url%2A> 属性。  
  
 除了 Uri 中的字符和数字以外，还需要支持字符。 例如，以下 URI 用于检索客户编号 "1/3812" 的客户信息：  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 请注意 Uri （% 2F）中的百分号编码的斜杠。 这是必需的，因为在这种情况下，斜杠字符表示数据而不是路径分隔符。  
  
 将字符串传递到 Uri 构造函数将导致以下 URI：  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 将路径拆分为其段将导致以下元素：  
  
 `Customer('1`  
  
 `3812')`  
  
 这不是请求发送方的意图。  
  
 如果将**unescapeRequestUrl**特性设置为**false**，则当 <xref:System.Net.HttpListener> 收到请求时，它将使用原始 URI，而不是将转换后的 uri 作为 <xref:System.Net.HttpListenerRequest.Url%2A> 属性的输入 `http.sys`。  
  
 **UnescapeRequestUrl**属性的默认值为**true**。  
  
 <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> 属性可用于从适用的配置文件中获取**unescapeRequestUrl**属性的当前值。  
  
## <a name="example"></a>示例  
 下面的示例演示如何配置 <xref:System.Net.HttpListener> 类，以便在接收到使用原始 URI 而不是将转换的 URI 从 `http.sys` 作为输入 <xref:System.Net.HttpListenerRequest.Url%2A> 属性的请求时配置。  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a>元素信息  
  
|||
|-|-|  
|Namespace|System.Net|  
|架构名称||  
|验证文件||  
|可以为空||  
  
## <a name="see-also"></a>请参阅

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [网络设置架构](index.md)
