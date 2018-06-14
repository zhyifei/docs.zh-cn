---
title: 如何：创建支持 AJAX 的 WCF 服务和访问该服务的 ASP.NET 客户端
ms.date: 03/30/2017
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 58971d11ab76112627dd81d53381236932268e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490625"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>如何：创建支持 AJAX 的 WCF 服务和访问该服务的 ASP.NET 客户端
本主题演示如何使用 Visual Studio 2008 创建启用了 AJAX 的 Windows Communication Foundation (WCF) 服务和 ASP.NET 客户端访问该服务。 在“过程”一节中描述了创建服务和客户端的代码的步骤之后，在“示例”一节中提供了相应的代码。  
  
### <a name="to-create-the-aspnet-client-application"></a>创建 ASP.NET 客户端应用程序  
  
1.  打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
2.  从**文件**菜单上，选择**新建**，然后**项目**，然后**Web**，然后选择**ASP.NET Web 应用程序**.  
  
3.  将项目`SandwichServices`单击**确定**。  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a>创建 WCF 支持 AJAX 的服务  
  
1.  右键单击`SandwichServices`项目中**解决方案资源管理器**窗口，然后选择**添加**，然后**新项**，，然后**启用了 AJAX 的 WCF 服务**.  
  
2.  将服务`CostService`中**名称**框中，单击**添加**。  
  
3.  打开 CostService.svc.cs 文件。  
  
4.  指定`Namespace`为<xref:System.ServiceModel.ServiceContractAttribute>作为`SandwichService`:  
  
    ```  
    namespace SandwichServices  
    {  
      [ServiceContract(Namespace = "SandwichServices")]  
      [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
       public class CostService  
       {  
         …  
       }  
     }  
    ```  
  
5.  在服务中实现操作。 将 <xref:System.ServiceModel.OperationContractAttribute> 添加到每个操作，以指定这些操作属于协定的一部分。 下面的示例实现一个返回给定数量的三明治的费用的方法。  
  
    ```  
    public class CostService  
    {  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
    // Add more operations here and mark them with [OperationContract]  
    }  
    ```  
  
### <a name="to-configure-the-client-to-access-the-service"></a>配置客户端以访问服务  
  
1.  打开 Default.aspx 页并选择**设计**视图。  
  
2.  从**视图**菜单上，选择**工具箱**。  
  
3.  展开**AJAX Extensions**节点和拖放**ScriptManager**到 Default.aspx 页。  
  
4.  右键单击**ScriptManager**和选择**属性**。  
  
5.  展开**服务**中的集合**属性**窗口以打开**ServiceReference 集合编辑器**窗口。  
  
6.  单击**添加**，指定`CostService.svc`作为**路径**引用，并且单击**确定**。  
  
7.  展开**HTML**中的节点**工具箱**和拖放**Input (Button)** 到 Default.aspx 页。  
  
8.  右键单击**按钮**和选择**属性**。  
  
9. 更改**值**字段`Price for 3 Sandwiches`。  
  
10. 双击**按钮**以访问 JavaScript 代码。  
  
11. 中的以下 JavaScript 代码传递 <`script`> 元素。  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a>从客户端访问服务  
  
1.  使用 Ctrl +F5 启动服务和 Web 客户端。 单击**3 份三明治的价格**按钮以生成预期的输出为"3.75"。  
  
## <a name="example"></a>示例  
 本示例包含 WCFService.svc.cs 文件中的服务代码和 Default.aspx 文件中的客户端代码。  
  
```  
//The service code contained in the CostService.svc.cs file.  
  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace SandwichServices  
{  
    [ServiceContract(Namespace="SandwichServices")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class CostService  
    {  
        // Add [WebGet] attribute to use HTTP GET  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
        // Add more operations here and mark them with [OperationContract]  
    }  
}  
//The code for hosting the service is contained in the CostService.svc file.  
  
<%@ ServiceHost Language="C#" Debug="true" Service="SandwichServices.CostService" CodeBehind="CostService.svc.cs" %>  
  
//The client code contained in the Default.aspx file.  
  
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="SandwichServices._Default" %>  
  
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">  
  
<html >  
<head runat="server">  
    <title>Untitled Page</title>  
<script language="javascript" type="text/javascript">  
// <!CDATA[  
  
function Button1_onclick() {  
var service = new SandwichServices.CostService();  
service.CostOfSandwiches(3, onSuccess, null, null);  
}  
  
function onSuccess(result){  
alert(result);  
}  
  
// ]]>  
</script>  
</head>  
<body>  
    <form id="form1" runat="server">  
    <div>  
  
    </div>  
    <asp:ScriptManager ID="ScriptManager1" runat="server">  
        <services>  
            <asp:servicereference Path="CostService.svc" />  
        </services>  
    </asp:ScriptManager>  
    </form>  
    <p>  
        <input id="Button1" type="button" value="Price for 3 Sandwiches" onclick="return Button1_onclick()" /></p>  
</body>  
</html>  
```     
