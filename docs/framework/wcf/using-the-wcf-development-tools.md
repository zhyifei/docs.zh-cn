---
title: "使用 WCF 开发工具"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f752d2aa2621ff650c864b2aca0928c5244c4917
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="1db0b-102">使用 WCF 开发工具</span><span class="sxs-lookup"><span data-stu-id="1db0b-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="1db0b-103">本节描述有助于开发 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 服务的 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 开发工具。</span><span class="sxs-lookup"><span data-stu-id="1db0b-103">This section describes the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)] development tools that can assist you in developing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.</span></span>  
  
 <span data-ttu-id="1db0b-104">可以以 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 模板为基础快速生成自己的服务，然后使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务自动主机和 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端对您的服务进行调试和测试。</span><span class="sxs-lookup"><span data-stu-id="1db0b-104">You can use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] templates as a foundation to quickly build your own service, then use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to debug and test your service.</span></span> <span data-ttu-id="1db0b-105">通过一起使用这些工具，可以快速完美地完成调试和测试过程，无需在早期阶段提交给承载模型。</span><span class="sxs-lookup"><span data-stu-id="1db0b-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="1db0b-106">WCF 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="1db0b-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="1db0b-107">WCF Visual Studio 模板</span><span class="sxs-lookup"><span data-stu-id="1db0b-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="1db0b-108">可以在 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中使用预定义的 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 项目和项模板快速生成 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务和周边应用程序。</span><span class="sxs-lookup"><span data-stu-id="1db0b-108">You can use the predefined [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project and item templates in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to quickly build [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="1db0b-109">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="1db0b-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="1db0b-110">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务自动主机 (WcfSvcHost.exe) 允许您启动 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 调试器 (F5) 以自动承载和测试已实现的服务。</span><span class="sxs-lookup"><span data-stu-id="1db0b-110">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (WcfSvcHost.exe) allows you to launch the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="1db0b-111">然后可以使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端 (wcfTestClient.exe) 或您自己的客户端来测试服务，以查找并解决任何潜在错误。</span><span class="sxs-lookup"><span data-stu-id="1db0b-111">You can then test the service using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="1db0b-112">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="1db0b-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1db0b-113"> 测试客户端 (WcfTestClient.exe) 是一个 GUI 工具，通过使用该工具，可以输入任意类型的参数、将该输入提交给服务并查看服务发回的响应。</span><span class="sxs-lookup"><span data-stu-id="1db0b-113"> Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="1db0b-114">当与 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务自动主机结合时，它可以提供完美的服务测试体验。</span><span class="sxs-lookup"><span data-stu-id="1db0b-114">It provides a seamless service testing experience when combined with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host.</span></span>  
  
 [<span data-ttu-id="1db0b-115">通过 XML 生成数据类型类</span><span class="sxs-lookup"><span data-stu-id="1db0b-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="1db0b-116">可将存储在剪贴板中的 XML 数据粘贴到代码页中。</span><span class="sxs-lookup"><span data-stu-id="1db0b-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="1db0b-117">数据中定义的类将被转换为代码类型。</span><span class="sxs-lookup"><span data-stu-id="1db0b-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="1db0b-118">在无管理员权限的情况下使用工具</span><span class="sxs-lookup"><span data-stu-id="1db0b-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="1db0b-119">为了使没有管理员权限的用户能够开发 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务，在安装 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 的过程中为命名空间“http://+:8731/Design_Time_Addresses”创建了一个 ACL（访问控制列表）。</span><span class="sxs-lookup"><span data-stu-id="1db0b-119">To enable users without administrator privilege to develop [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="1db0b-120">该 ACL 被设置为“(UI)”，这将包括登录到此计算机的所有交互用户。</span><span class="sxs-lookup"><span data-stu-id="1db0b-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="1db0b-121">管理员可以在此 ACL 中添加或移除用户，或者打开其他端口。此 ACL 支持 WCF 或 WF 模板以其各自的默认配置发送和接收数据。</span><span class="sxs-lookup"><span data-stu-id="1db0b-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="1db0b-122">它还使用户能够使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务自动主机 (wcfSvcHost.exe)，而无需向他们授予管理员权限。</span><span class="sxs-lookup"><span data-stu-id="1db0b-122">It also enables users to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="1db0b-123">可以使用提升的管理员帐户在 [!INCLUDE[wv](../../../includes/wv-md.md)] 中通过 Netsh.exe 工具来修改访问权限。</span><span class="sxs-lookup"><span data-stu-id="1db0b-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="1db0b-124">下面是使用 Netsh.exe 的示例。</span><span class="sxs-lookup"><span data-stu-id="1db0b-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="1db0b-125">Netsh.exe，请参阅[如何使用 Netsh.exe 工具和命令行开关](http://go.microsoft.com/fwlink/?LinkId=97877)。</span><span class="sxs-lookup"><span data-stu-id="1db0b-125"> Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db0b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1db0b-126">See Also</span></span>  
 [<span data-ttu-id="1db0b-127">WCF Visual Studio 模板</span><span class="sxs-lookup"><span data-stu-id="1db0b-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="1db0b-128">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="1db0b-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="1db0b-129">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="1db0b-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
