---
title: "如何：创建支持 AJAX 的 WCF 服务和访问该服务的 ASP.NET 客户端"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a45a186b0d281976f3d6ad554d75742ba0f1cd50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="36bc8-102">如何：创建支持 AJAX 的 WCF 服务和访问该服务的 ASP.NET 客户端</span><span class="sxs-lookup"><span data-stu-id="36bc8-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>
<span data-ttu-id="36bc8-103">本主题演示如何使用 Visual Studio 2008 创建一个支持 AJAX 的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务和一个访问该服务的 ASP.NET 客户端。</span><span class="sxs-lookup"><span data-stu-id="36bc8-103">This topic shows how to use Visual Studio 2008 to create an AJAX-enabled [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and an ASP.NET client that accesses the service.</span></span> <span data-ttu-id="36bc8-104">在“过程”一节中描述了创建服务和客户端的代码的步骤之后，在“示例”一节中提供了相应的代码。</span><span class="sxs-lookup"><span data-stu-id="36bc8-104">The code for the service and for the client are provided in the Example section after the steps for creating them are described in the Procedures section.</span></span>  
  
### <a name="to-create-the-aspnet-client-application"></a><span data-ttu-id="36bc8-105">创建 ASP.NET 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="36bc8-105">To create the ASP.NET client application</span></span>  
  
1.  <span data-ttu-id="36bc8-106">打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="36bc8-106">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="36bc8-107">从**文件**菜单上，选择**新建**，然后**项目**，然后**Web**，然后选择**ASP.NET Web 应用程序**.</span><span class="sxs-lookup"><span data-stu-id="36bc8-107">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Application**.</span></span>  
  
3.  <span data-ttu-id="36bc8-108">将项目`SandwichServices`单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="36bc8-108">Name the Project `SandwichServices` and click **OK**.</span></span>  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a><span data-ttu-id="36bc8-109">创建 WCF 支持 AJAX 的服务</span><span class="sxs-lookup"><span data-stu-id="36bc8-109">To create the WCF AJAX-enabled service</span></span>  
  
1.  <span data-ttu-id="36bc8-110">右键单击`SandwichServices`项目中**解决方案资源管理器**窗口，然后选择**添加**，然后**新项**，，然后**启用了 AJAX 的 WCF 服务**.</span><span class="sxs-lookup"><span data-stu-id="36bc8-110">Right-click the `SandwichServices` project in the **Solution Explorer** window and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>  
  
2.  <span data-ttu-id="36bc8-111">将服务`CostService`中**名称**框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="36bc8-111">Name the service `CostService` in the **Name** box and click **Add**.</span></span>  
  
3.  <span data-ttu-id="36bc8-112">打开 CostService.svc.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="36bc8-112">Open the CostService.svc.cs file.</span></span>  
  
4.  <span data-ttu-id="36bc8-113">指定`Namespace`为<xref:System.ServiceModel.ServiceContractAttribute>作为`SandwichService`:</span><span class="sxs-lookup"><span data-stu-id="36bc8-113">Specify the `Namespace` for <xref:System.ServiceModel.ServiceContractAttribute> as `SandwichService`:</span></span>  
  
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
  
5.  <span data-ttu-id="36bc8-114">在服务中实现操作。</span><span class="sxs-lookup"><span data-stu-id="36bc8-114">Implement the operations in the service.</span></span> <span data-ttu-id="36bc8-115">将 <xref:System.ServiceModel.OperationContractAttribute> 添加到每个操作，以指定这些操作属于协定的一部分。</span><span class="sxs-lookup"><span data-stu-id="36bc8-115">Add the <xref:System.ServiceModel.OperationContractAttribute> to each of the operations to indicate that they are part of the contract.</span></span> <span data-ttu-id="36bc8-116">下面的示例实现一个返回给定数量的三明治的费用的方法。</span><span class="sxs-lookup"><span data-stu-id="36bc8-116">The following example implements a method that returns the cost of a given quantity of sandwiches.</span></span>  
  
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
  
### <a name="to-configure-the-client-to-access-the-service"></a><span data-ttu-id="36bc8-117">配置客户端以访问服务</span><span class="sxs-lookup"><span data-stu-id="36bc8-117">To configure the client to access the service</span></span>  
  
1.  <span data-ttu-id="36bc8-118">打开 Default.aspx 页并选择**设计**视图。</span><span class="sxs-lookup"><span data-stu-id="36bc8-118">Open the Default.aspx page and select the **Design** view.</span></span>  
  
2.  <span data-ttu-id="36bc8-119">从**视图**菜单上，选择**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="36bc8-119">From the **View** menu, select **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="36bc8-120">展开**AJAX Extensions**节点和拖放**ScriptManager**到 Default.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="36bc8-120">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** on to the Default.aspx page.</span></span>  
  
4.  <span data-ttu-id="36bc8-121">右键单击**ScriptManager**和选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="36bc8-121">Right-click the **ScriptManager** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="36bc8-122">展开**服务**中的集合**属性**窗口以打开**ServiceReference 集合编辑器**窗口。</span><span class="sxs-lookup"><span data-stu-id="36bc8-122">Expand the **Services** collection in the **Properties** window to open up the **ServiceReference Collection Editor** window.</span></span>  
  
6.  <span data-ttu-id="36bc8-123">单击**添加**，指定`CostService.svc`作为**路径**引用，并且单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="36bc8-123">Click **Add**, specify `CostService.svc` as the **Path** referenced, and click **OK**.</span></span>  
  
7.  <span data-ttu-id="36bc8-124">展开**HTML**中的节点**工具箱**和拖放**Input (Button)**到 Default.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="36bc8-124">Expand the **HTML** node in the **Toolbox** and drag and drop an **Input (Button)** on to the Default.aspx page.</span></span>  
  
8.  <span data-ttu-id="36bc8-125">右键单击**按钮**和选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="36bc8-125">Right-click the **Button** and select **Properties**.</span></span>  
  
9. <span data-ttu-id="36bc8-126">更改**值**字段`Price for 3 Sandwiches`。</span><span class="sxs-lookup"><span data-stu-id="36bc8-126">Change the **Value** field to `Price for 3 Sandwiches`.</span></span>  
  
10. <span data-ttu-id="36bc8-127">双击**按钮**以访问 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="36bc8-127">Double-click the **Button** to access the JavaScript code.</span></span>  
  
11. <span data-ttu-id="36bc8-128">中的以下 JavaScript 代码传递 <`script`> 元素。</span><span class="sxs-lookup"><span data-stu-id="36bc8-128">Pass in the following JavaScript code within the <`script`> element.</span></span>  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a><span data-ttu-id="36bc8-129">从客户端访问服务</span><span class="sxs-lookup"><span data-stu-id="36bc8-129">To access the service from the client</span></span>  
  
1.  <span data-ttu-id="36bc8-130">使用 Ctrl +F5 启动服务和 Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="36bc8-130">Use Ctrl +F5 to launch the service and the Web client.</span></span> <span data-ttu-id="36bc8-131">单击**3 份三明治的价格**按钮以生成预期的输出为"3.75"。</span><span class="sxs-lookup"><span data-stu-id="36bc8-131">Click the **Price for 3 Grilled Sandwiches** button to generate the expected output of "3.75".</span></span>  
  
## <a name="example"></a><span data-ttu-id="36bc8-132">示例</span><span class="sxs-lookup"><span data-stu-id="36bc8-132">Example</span></span>  
 <span data-ttu-id="36bc8-133">本示例包含 WCFService.svc.cs 文件中的服务代码和 Default.aspx 文件中的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="36bc8-133">This example contains the service code contained in the WCFService.svc.cs file and the client code contained in the Default.aspx file.</span></span>  
  
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
