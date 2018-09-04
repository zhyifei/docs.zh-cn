---
title: 使用复杂类型的 AJAX 服务示例
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 4574e5d33ebed7184e229c71e03496db34a95575
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528280"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="82f76-102">使用复杂类型的 AJAX 服务示例</span><span class="sxs-lookup"><span data-stu-id="82f76-102">AJAX Service Using Complex Types Sample</span></span>
<span data-ttu-id="82f76-103">此示例演示如何使用 Windows Communication Foundation (WCF) 来创建用于创建复杂类型的实例，并将其发送服务和客户端作为 JavaScript 对象表示法 (JSON) 之间的 ASP.NET 异步 JavaScript 和 XML (AJAX) 服务。</span><span class="sxs-lookup"><span data-stu-id="82f76-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="82f76-104">可以从 Web 浏览器客户端使用 JavaScript 代码来访问 AJAX 服务。</span><span class="sxs-lookup"><span data-stu-id="82f76-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="82f76-105">此示例是基于[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例。</span><span class="sxs-lookup"><span data-stu-id="82f76-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="82f76-106">WCF 中的 AJAX 支持适用于与通过 ASP.NET AJAX 一起使用<xref:System.Web.UI.ScriptManager>控件。</span><span class="sxs-lookup"><span data-stu-id="82f76-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="82f76-107">使用 ASP.NET AJAX 使用 WCF 的示例，请参阅[AJAX 示例](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)。</span><span class="sxs-lookup"><span data-stu-id="82f76-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82f76-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="82f76-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="82f76-109">下面的示例中的服务是无代码的特定于 AJAX 的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="82f76-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="82f76-110">由于未应用 <xref:System.ServiceModel.Web.WebGetAttribute> 属性，因此将使用默认的 HTTP 谓词（“POST”）。</span><span class="sxs-lookup"><span data-stu-id="82f76-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="82f76-111">该服务有一个操作 `DoMath`，该操作返回一个名为 `MathResult` 的复杂类型。</span><span class="sxs-lookup"><span data-stu-id="82f76-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="82f76-112">该复杂类型是标准的数据协定类型，也不包含特定于 AJAX 的代码。</span><span class="sxs-lookup"><span data-stu-id="82f76-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 <span data-ttu-id="82f76-113">通过使用 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 在服务上创建 AJAX 终结点，就像在基本 AJAX 服务示例中一样。</span><span class="sxs-lookup"><span data-stu-id="82f76-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="82f76-114">客户端网页 ComplexTypeClientPage.aspx 包含 ASP.NET 和 JavaScript 代码来调用服务，当用户单击**执行计算**页上的按钮。</span><span class="sxs-lookup"><span data-stu-id="82f76-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="82f76-115">用于调用服务的代码构造 JSON 正文并发送它使用 HTTP POST，类似于[使用 HTTP POST 的 AJAX 服务](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)示例。</span><span class="sxs-lookup"><span data-stu-id="82f76-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
 <span data-ttu-id="82f76-116">在服务调用成功之后，您可以在所得到的 JavaScript 对象上访问各个数据成员（`sum`、`difference`、`product` 和 `quotient`）。</span><span class="sxs-lookup"><span data-stu-id="82f76-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="82f76-117">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="82f76-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="82f76-118">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="82f76-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="82f76-119">如中所述生成解决方案 ComplexTypeAjaxService.sln[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="82f76-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="82f76-120">导航到 http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx（不要打开 ComplexTypeClientPage.aspx 在浏览器中从项目目录中）。</span><span class="sxs-lookup"><span data-stu-id="82f76-120">Navigate to http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82f76-121">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="82f76-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="82f76-122">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="82f76-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="82f76-123">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="82f76-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82f76-124">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="82f76-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="82f76-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="82f76-125">See Also</span></span>  
 [<span data-ttu-id="82f76-126">基本 AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="82f76-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
