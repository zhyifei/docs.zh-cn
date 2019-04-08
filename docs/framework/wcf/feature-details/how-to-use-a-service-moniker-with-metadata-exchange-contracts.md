---
title: 如何：将服务名字对象与元数据交换协定一起使用
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: e1d6c6516294d7df7f8c89a3aaddcf2ac3ba0e2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082693"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="a4491-102">如何：将服务名字对象与元数据交换协定一起使用</span><span class="sxs-lookup"><span data-stu-id="a4491-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="a4491-103">在开发一些新的 WCF 服务之后, 可以决定你想要能够从脚本或 Visual Basic 6.0 应用程序中调用这些服务。</span><span class="sxs-lookup"><span data-stu-id="a4491-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="a4491-104">一种方法是生成 WCF 客户端程序集，向 COM 注册程序集、 程序集安装在 GAC 中，然后从 Visual Basic 代码中引用 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="a4491-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="a4491-105">当你将分发应用程序时，必须将分发的 WCF 客户端程序集。</span><span class="sxs-lookup"><span data-stu-id="a4491-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="a4491-106">然后，用户必须使用 COM 注册 WCF 客户端程序集，并且将该程序集放置在 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="a4491-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="a4491-107">WCF COM 互操作还可使相同的服务调用，而不依赖于 WCF 客户端程序集。</span><span class="sxs-lookup"><span data-stu-id="a4491-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="a4491-108">WCF 标记使您能够从任何 COM 兼容语言 （Visual Basic、 VBScript、 Visual Basic for Applications (VBA) 和等等） 可通过指定元数据交换 (Mex) 终结点的服务标记用于提取类型的 URI 调用任何 WCF 服务有关服务的信息。</span><span class="sxs-lookup"><span data-stu-id="a4491-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="a4491-109">本主题介绍如何调用使用指定 Mex 终结点的 WCF 名字对象的 WCF 入门示例。</span><span class="sxs-lookup"><span data-stu-id="a4491-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4491-110">永远不会实际实例化 WCF 客户端程序集所定义的类型。</span><span class="sxs-lookup"><span data-stu-id="a4491-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="a4491-111">该程序集只用于元数据。</span><span class="sxs-lookup"><span data-stu-id="a4491-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="a4491-112">使用带有 Mex 地址的服务标记</span><span class="sxs-lookup"><span data-stu-id="a4491-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="a4491-113">生成入门示例并使用 Internet Explorer 浏览至其 URL (http://localhost/ServiceModelSamples/Service.svc)以确保服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="a4491-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="a4491-114">生成 Visual Basic 脚本或包含以下代码的 Visual Basic 应用程序：</span><span class="sxs-lookup"><span data-stu-id="a4491-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="a4491-115">运行 Visual Basic 应用程序或脚本。</span><span class="sxs-lookup"><span data-stu-id="a4491-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4491-116">您所调用的服务必须公开标记的 Mex 终结点，以便能够从服务中读取元数据。</span><span class="sxs-lookup"><span data-stu-id="a4491-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="a4491-117">有关详细信息，请参阅[如何：发布使用配置文件服务的元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="a4491-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4491-118">如果标记格式不正确，或如果服务不可用，则对 `GetObject` 的调用将返回一个错误，指示“语法无效”。</span><span class="sxs-lookup"><span data-stu-id="a4491-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="a4491-119">如果您收到此错误，请确保所使用的标记正确无误且服务可用。</span><span class="sxs-lookup"><span data-stu-id="a4491-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4491-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4491-120">See also</span></span>

- [<span data-ttu-id="a4491-121">如何：使用未注册的 Windows Communication Foundation 服务名字对象</span><span class="sxs-lookup"><span data-stu-id="a4491-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="a4491-122">如何：将服务名字对象用于 WSDL 协定</span><span class="sxs-lookup"><span data-stu-id="a4491-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
