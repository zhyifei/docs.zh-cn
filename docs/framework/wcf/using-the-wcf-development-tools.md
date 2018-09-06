---
title: 使用 WCF 开发工具
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 3eb349fd795b2067d4d75ff138fd9b5922110bd3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037872"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="d41c3-102">使用 WCF 开发工具</span><span class="sxs-lookup"><span data-stu-id="d41c3-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="d41c3-103">本部分介绍可以帮助您开发 WCFservice 的 Visual Studio 开发工具。</span><span class="sxs-lookup"><span data-stu-id="d41c3-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="d41c3-104">您可以使用作为基础的 Visual Studio 模板快速生成你自己的服务，然后使用 WCF 服务自动主机和 WCF 测试客户端来调试和测试你的服务。</span><span class="sxs-lookup"><span data-stu-id="d41c3-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="d41c3-105">通过一起使用这些工具，可以快速完美地完成调试和测试过程，无需在早期阶段提交给承载模型。</span><span class="sxs-lookup"><span data-stu-id="d41c3-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="d41c3-106">WCF 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="d41c3-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="d41c3-107">WCF Visual Studio 模板</span><span class="sxs-lookup"><span data-stu-id="d41c3-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="d41c3-108">可以使用 Visual Studio 中的预定义的 Visual Studio 项目和项模板快速生成 WCF 服务和周边应用程序。</span><span class="sxs-lookup"><span data-stu-id="d41c3-108">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="d41c3-109">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="d41c3-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="d41c3-110">WCF 服务自动主机 (WcfSvcHost.exe) 允许您启动 Visual Studio 调试器 (F5) 以自动承载和测试已实现的服务。</span><span class="sxs-lookup"><span data-stu-id="d41c3-110">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="d41c3-111">然后，您可以测试使用 WCF 测试客户端 (wcfTestClient.exe) 或自己的客户端查找并解决任何潜在错误的服务。</span><span class="sxs-lookup"><span data-stu-id="d41c3-111">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="d41c3-112">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="d41c3-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="d41c3-113">WCF 测试客户端 (WcfTestClient.exe) 是一个 GUI 工具，您可以输入任意类型的参数，将该服务，以及查看发回响应服务输入提交。</span><span class="sxs-lookup"><span data-stu-id="d41c3-113">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="d41c3-114">它提供了完美的服务测试体验与 WCF 服务自动主机结合使用时。</span><span class="sxs-lookup"><span data-stu-id="d41c3-114">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="d41c3-115">通过 XML 生成数据类型类</span><span class="sxs-lookup"><span data-stu-id="d41c3-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="d41c3-116">可将存储在剪贴板中的 XML 数据粘贴到代码页中。</span><span class="sxs-lookup"><span data-stu-id="d41c3-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="d41c3-117">数据中定义的类将被转换为代码类型。</span><span class="sxs-lookup"><span data-stu-id="d41c3-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="d41c3-118">在无管理员权限的情况下使用工具</span><span class="sxs-lookup"><span data-stu-id="d41c3-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="d41c3-119">若要使不具有管理员权限的用户能够开发 WCF 服务，ACL （访问控制列表） 创建命名空间"http://+:8731/Design_Time_Addresses"在 Visual Studio 安装的过程。</span><span class="sxs-lookup"><span data-stu-id="d41c3-119">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="d41c3-120">该 ACL 被设置为“(UI)”，这将包括登录到此计算机的所有交互用户。</span><span class="sxs-lookup"><span data-stu-id="d41c3-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="d41c3-121">管理员可以在此 ACL 中添加或移除用户，或者打开其他端口。此 ACL 支持 WCF 或 WF 模板以其各自的默认配置发送和接收数据。</span><span class="sxs-lookup"><span data-stu-id="d41c3-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="d41c3-122">它还使用户能够使用 WCF 服务自动主机 (wcfSvcHost.exe) 而无需向其授予管理员权限。</span><span class="sxs-lookup"><span data-stu-id="d41c3-122">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="d41c3-123">可以使用提升的管理员帐户在 [!INCLUDE[wv](../../../includes/wv-md.md)] 中通过 Netsh.exe 工具来修改访问权限。</span><span class="sxs-lookup"><span data-stu-id="d41c3-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="d41c3-124">下面是使用 Netsh.exe 的示例。</span><span class="sxs-lookup"><span data-stu-id="d41c3-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="d41c3-125">有关 Netsh.exe 的详细信息，请参阅[如何使用 Netsh.exe 工具和命令行开关](https://go.microsoft.com/fwlink/?LinkId=97877)。</span><span class="sxs-lookup"><span data-stu-id="d41c3-125">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41c3-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d41c3-126">See Also</span></span>  
 [<span data-ttu-id="d41c3-127">WCF Visual Studio 模板</span><span class="sxs-lookup"><span data-stu-id="d41c3-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="d41c3-128">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="d41c3-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="d41c3-129">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="d41c3-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
