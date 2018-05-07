---
title: 如何：将启用了 AJAX 的 ASP.NET Web 服务迁移到 WCF
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 048408adf8678c243a225a233cb1173c9b7f869f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>如何：将启用了 AJAX 的 ASP.NET Web 服务迁移到 WCF
本主题概述了基本的 ASP.NET AJAX 服务迁移到等效的启用了 AJAX 的 Windows Communication Foundation (WCF) 服务的过程。 它演示如何创建 ASP.NET AJAX 服务的功能上等效 WCF 版本。 然后可以并排比较，使用这两项服务或 WCF 服务可以用于替换 ASP.NET AJAX 服务。  
  
 迁移现有的 ASP.NET AJAX 的 WCF AJAX 服务的服务为你提供了以下好处：  
  
-   只需最少的额外配置，即可将 AJAX 服务公开为 SOAP 服务。  
  
-   你可以从跟踪，如 WCF 功能中获益，依此类推。  
  
 下面的过程假定您正在使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
 从本主题概述的过程中得到的代码将在过程后面的示例中提供。  
  
 有关公开通过支持 AJAX 的终结点的 WCF 服务的详细信息，请参阅[如何： 使用配置来添加 ASP.NET AJAX 终结点](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)主题。  
  
### <a name="to-create-and-test-the-aspnet-web-service-application"></a>创建并测试 ASP.NET Web 服务应用程序  
  
1.  打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
2.  从**文件**菜单上，选择**新建**，然后**项目**，然后**Web**，然后选择**ASP.NET Web 服务应用程序**.  
  
3.  将项目`ASPHello`单击**确定**。  
  
4.  在 Service1.asmx.cs 文件中，取消对包含 `System.Web.Script.Services.ScriptService]` 的行的注释，以便为此服务启用 AJAX。  
  
5.  从**生成**菜单上，选择**生成解决方案**。  
  
6.  从**调试**菜单上，选择**启动但不调试**。  
  
7.  在生成的网页上，选择 `HelloWorld` 操作。  
  
8.  单击**Invoke**按钮上`HelloWorld`测试页。 您应收到以下 XML 响应。  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. 此响应可确认您现在已拥有一项能正常运行的 ASP.NET AJAX 服务。具体而言，该服务现在已在 Service1.asmx/HelloWorld 处公开了一个响应 HTTP POST 请求并返回 XML 的终结点。  
  
     现在你已准备好转换此服务以使用 WCF AJAX 服务。  
  
### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>创建等效的 WCF AJAX 服务应用程序  
  
1.  右键单击**ASPHello**项目，然后选择**添加**，然后**新项**，，然后**启用了 AJAX 的 WCF 服务**。  
  
2.  将服务`WCFHello`单击**添加**。  
  
3.  打开 WCFHello.svc.cs 文件。  
  
4.  在 Service1.asmx.cs 中，将复制的以下实现`HelloWorld`操作。  
  
    ```  
    public string HelloWorld()  
    {  
         return "Hello World";  
    }  
    ```  
  
5.  复制的实现粘贴`HelloWorld`到 WCFHello.svc.cs 文件中替换下面的代码的操作。  
  
    ```  
    public void DoWork()  
    {  
          // Add your operation implementation here  
          return;  
    }  
    ```  
  
6.  指定`Namespace`属性，则为<xref:System.ServiceModel.ServiceContractAttribute>作为`WCFHello`。  
  
    ```  
    [ServiceContract(Namespace="WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]  
    public class WCFHello  
    { … }  
    ```  
  
7.  添加<xref:System.ServiceModel.Web.WebInvokeAttribute>到`HelloWorld`操作和组<xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>属性以返回<xref:System.ServiceModel.Web.WebMessageFormat.Xml>。 请注意，如果未设置此属性，则默认返回类型为 <xref:System.ServiceModel.Web.WebMessageFormat.Json>。  
  
    ```  
    [OperationContract]  
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
    public string HelloWorld()  
    {  
        return "Hello World";  
    }  
    ```  
  
8.  从**生成**菜单上，选择**生成解决方案**。  
  
9. 打开 WCFHello.svc 文件和从**调试**菜单上，选择**启动但不调试**。  
  
10. 服务现在公开一个终结点位于`WCFHello.svc/HelloWorld`，该响应 HTTP POST 请求。 HTTP POST 请求不能从浏览器进行测试，但终结点会返回以下 XML。  
  
    ```xml  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. `WCFHello.svc/HelloWorld`和`Service1.aspx/HelloWorld`终结点现在在功能上等效。  
  
## <a name="example"></a>示例  
 从本主题概述的过程中得到的代码将在下面的示例中提供。  
  
```  
//This is the ASP.NET code in the Service1.asmx.cs file.  
  
using System;  
using System.Collections;  
using System.ComponentModel;  
using System.Data;  
using System.Linq;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Linq;  
using System.Web.Script.Services;  
  
namespace ASPHello  
{  
    /// <summary>  
    /// Summary description for Service1.  
    /// </summary>  
    [WebService(Namespace = "http://tempuri.org/")]  
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
    [ToolboxItem(false)]  
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.   
    [System.Web.Script.Services.ScriptService]  
    public class Service1 : System.Web.Services.WebService  
    {  
  
        [WebMethod]  
        public string HelloWorld()  
        {  
            return "Hello World";  
        }  
    }  
}   
  
//This is the WCF code in the WCFHello.svc.cs file.  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace ASPHello  
{  
    [ServiceContract(Namespace = "WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class WCFHello  
    {  
        // Add [WebInvoke] attribute to use HTTP GET.  
        [OperationContract]  
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
        public string HelloWorld()  
        {  
            return "Hello World";  
        }  
  
        // Add more operations here and mark them with [OperationContract].  
    }  
}  
```  
  
 <xref:System.Xml.XmlDocument> 不支持 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 类型，因为此类型不能被 <xref:System.Xml.Serialization.XmlSerializer> 序列化。 可以改用 <xref:System.Xml.Linq.XDocument> 类型或序列化 <xref:System.Xml.XmlDocument.DocumentElement%2A>。  
  
 如果正在升级 ASMX Web 服务，并通过并行迁移到 WCF 服务，避免将两种类型映射到客户端上的相同名称。 如果 <xref:System.Web.Services.WebMethodAttribute> 和 <xref:System.ServiceModel.ServiceContractAttribute> 中使用了同一类型，则这将导致序列化程序中出现异常：  
  
-   如果首先添加 WCF 服务，则对 ASMX Web 服务调用方法将导致异常中的<xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29>因为代理中顺序的 WCF 样式定义优先。  
  
-   如果首先添加 ASMX Web 服务，则将调用 WCF 服务上的方法导致异常中的<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>因为代理中顺序的 Web 服务样式定义优先。  
  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 和 ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> 在行为上存在很大差异。 例如，<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 将字典表示为键/值对的数组，而 ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> 则将字典表示为实际的 JSON 对象。 因此，下面是用 ASP.NET AJAX 表示的字典。  
  
```  
Dictionary<string, int> d = new Dictionary<string, int>();  
d.Add("one", 1);  
d.Add("two", 2);  
```  
  
 在下面的列表中：此字典用 JSON 对象表示：  
  
-   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 将其表示为 [{"Key":"one","Value":1},{"Key":"two","Value":2}]  
  
-   {"one": 1，"two": 2} ASP.NET ajax <xref:System.Web.Script.Serialization.JavaScriptSerializer>  
  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 可以处理其中的键类型不是字符串的词典，而 <xref:System.Web.Script.Serialization.JavaScriptSerializer> 则无法处理，在这一方面前者的功能更为强大。 但后者与 JSON 的兼容性更好。  
  
 下表汇总了这些序列化程序之间的重大差异。  
  
|差异类别|DataContractJsonSerializer|ASP.NET AJAX JavaScriptSerializer|  
|-----------------------------|--------------------------------|---------------------------------------|  
|将空缓冲区（新 byte[0]）反序列化为 <xref:System.Object>（或 <xref:System.Uri>，或某些其他类）。|SerializationException|null|  
|<xref:System.DBNull.Value> 的序列化|{} (或 {"__type":"#System"})|null|  
|[Serializable] 类型的私有成员的序列化。|已序列化|未序列化|  
|<xref:System.Runtime.Serialization.ISerializable> 类型的公共属性的序列化。|未序列化|已序列化|  
|JSON 的“扩展”|遵循 JSON 规范，该规范要求为对象成员名称加上引号 ({"a":"hello"})。|支持不带引号的对象成员名称 ({a:"hello"})。|  
|<xref:System.DateTime> 协调世界时 (UTC)|不支持格式"\\/Date(123456789U)\\/"或"\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))？\\)\\\\/)".|支持格式"\\/Date(123456789U)\\/"和"\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))？\\)\\ \\/)"作为 DateTime 值。|  
|词典的表示形式|数组 KeyValuePair\<K，V >，处理不是字符串的密钥类型。|作为实际的 JSON 对象 - 但仅处理是字符串的键类型。|  
|转义符|始终应带有转义正斜杠 (/)；切勿使用非转义的无效 JSON 字符，例如“\n”。|对于 DateTime 值，带有转义正斜杠 (/)。|  
  
## <a name="see-also"></a>请参阅  
 [如何：使用配置来添加 ASP.NET AJAX 终结点](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
