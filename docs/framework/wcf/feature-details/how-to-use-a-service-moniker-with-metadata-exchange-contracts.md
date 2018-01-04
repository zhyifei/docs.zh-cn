---
title: "如何：将服务标记与元数据交换协定一起使用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d2b5b6d4a671a3eb281f49dd60fd3c00ee76f8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="b90a5-102">如何：将服务标记与元数据交换协定一起使用</span><span class="sxs-lookup"><span data-stu-id="b90a5-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="b90a5-103">在开发了一些新的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务后，您也许会决定希望能够从脚本或 Visual Basic 6.0 应用程序中调用这些服务。</span><span class="sxs-lookup"><span data-stu-id="b90a5-103">After developing some new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="b90a5-104">为此，您可以先生成一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端程序集，然后使用 COM 注册该程序集，再将该程序集安装在 GAC 中，然后从您的 Visual Basic 代码中引用 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="b90a5-104">One method would be to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="b90a5-105">在您分发应用程序时，您必须同时分发 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端程序集。</span><span class="sxs-lookup"><span data-stu-id="b90a5-105">When you distribute the application, you will have to distribute the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client assembly as well.</span></span> <span data-ttu-id="b90a5-106">然后，用户必须使用 COM 注册 WCF 客户端程序集，并且将该程序集放置在 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="b90a5-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b90a5-107"> COM 互操作使您在不依赖 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端程序集的情况下，也能够完成相同的服务调用。</span><span class="sxs-lookup"><span data-stu-id="b90a5-107"> COM Interop also allows you to make the same service calls without relying on a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly.</span></span> <span data-ttu-id="b90a5-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 标记使您能够从任何与 COM 兼容的语言（Visual Basic、VBScript、Visual Basic for Applications (VBA) 等）中调用任何 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务，方法是通过指定服务标记用于提取有关该服务的类型信息的元数据交换 (Mex) 终结点 URI。</span><span class="sxs-lookup"><span data-stu-id="b90a5-108">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker allows you to call any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="b90a5-109">本主题描述如何使用指定 Mex 终结点的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 标记调用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 入门示例。</span><span class="sxs-lookup"><span data-stu-id="b90a5-109">This topic describes how to call the Getting Started [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b90a5-110">实际上，从不实例化由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端程序集定义的类型。</span><span class="sxs-lookup"><span data-stu-id="b90a5-110">The types defined by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly are never actually instantiated.</span></span> <span data-ttu-id="b90a5-111">该程序集只用于元数据。</span><span class="sxs-lookup"><span data-stu-id="b90a5-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="b90a5-112">使用带有 Mex 地址的服务标记</span><span class="sxs-lookup"><span data-stu-id="b90a5-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="b90a5-113">生成入门示例并使用 Internet Explorer 浏览至其 URL (http://localhost/ServiceModelSamples/Service.svc) 以确保服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="b90a5-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="b90a5-114">生成 Visual Basic 脚本或包含以下代码的 Visual Basic 应用程序：</span><span class="sxs-lookup"><span data-stu-id="b90a5-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="b90a5-115">运行 Visual Basic 应用程序或脚本。</span><span class="sxs-lookup"><span data-stu-id="b90a5-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b90a5-116">您所调用的服务必须公开标记的 Mex 终结点，以便能够从服务中读取元数据。</span><span class="sxs-lookup"><span data-stu-id="b90a5-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="b90a5-117">有关详细信息，请参阅[如何： 使用配置文件服务的发布元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="b90a5-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b90a5-118">如果标记格式不正确，或如果服务不可用，则对 `GetObject` 的调用将返回一个错误，指示“语法无效”。</span><span class="sxs-lookup"><span data-stu-id="b90a5-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="b90a5-119">如果您收到此错误，请确保所使用的标记正确无误且服务可用。</span><span class="sxs-lookup"><span data-stu-id="b90a5-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b90a5-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b90a5-120">See Also</span></span>  
 [<span data-ttu-id="b90a5-121">如何：使用未注册的 Windows Communication Foundation 服务名字对象</span><span class="sxs-lookup"><span data-stu-id="b90a5-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [<span data-ttu-id="b90a5-122">如何：将服务名字对象用于 WSDL 协定</span><span class="sxs-lookup"><span data-stu-id="b90a5-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
