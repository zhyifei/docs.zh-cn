---
title: 使用 WCF 开发工具
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183080"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="2fe5a-102">使用 WCF 开发工具</span><span class="sxs-lookup"><span data-stu-id="2fe5a-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="2fe5a-103">本节介绍可视化工作室开发工具，这些工具可帮助您开发 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="2fe5a-104">您可以使用 Visual Studio 模板作为基础来快速构建您自己的服务，然后使用 WCF 服务自动主机和 WCF 测试客户端来调试和测试服务。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="2fe5a-105">通过一起使用这些工具，可以快速完美地完成调试和测试过程，无需在早期阶段提交给承载模型。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="2fe5a-106">从 Visual Studio 2017 开始，默认情况下不会安装 WCF 开发工具。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="2fe5a-107">为了使用这些功能，必须确保在可视化工作室安装程序中选择 Windows 通信基础组件。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="2fe5a-108">WCF 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="2fe5a-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="2fe5a-109">WCF Visual Studio 模板</span><span class="sxs-lookup"><span data-stu-id="2fe5a-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="2fe5a-110">您可以使用 Visual Studio 中预定义的 Visual Studio 项目和项目模板来快速构建 WCF 服务和周围应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="2fe5a-111">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="2fe5a-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="2fe5a-112">WCF 服务自动主机 （WcfSvcHost.exe） 允许您启动 Visual Studio 调试器 （F5） 以自动托管和测试您已实现的服务。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="2fe5a-113">然后，您可以使用 WCF 测试客户端 （wcfTestClient.exe） 或您自己的客户端测试服务，以查找和修复任何潜在错误。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="2fe5a-114">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="2fe5a-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="2fe5a-115">WCF 测试客户端 （WcfTestClient.exe） 是一个 GUI 工具，允许您输入任意类型的参数，将该输入提交到服务，并查看服务发送回的响应。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="2fe5a-116">与 WCF 服务自动主机结合使用时，可提供无缝的服务测试体验。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="2fe5a-117">从 XML 生成数据类型类</span><span class="sxs-lookup"><span data-stu-id="2fe5a-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="2fe5a-118">可将存储在剪贴板中的 XML 数据粘贴到代码页中。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="2fe5a-119">数据中定义的类将被转换为代码类型。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="2fe5a-120">在无管理员权限的情况下使用工具</span><span class="sxs-lookup"><span data-stu-id="2fe5a-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="2fe5a-121">为了使没有管理员权限的用户能够开发 WCF 服务，在安装 Visual Studio 期间为命名空间"http://+:8731/Design_Time_Addresses创建 ACL（访问控制列表）。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="2fe5a-122">该 ACL 被设置为“(UI)”，这将包括登录到此计算机的所有交互用户。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="2fe5a-123">管理员可以在此 ACL 中添加或移除用户，或者打开其他端口。此 ACL 支持 WCF 或 WF 模板以其各自的默认配置发送和接收数据。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="2fe5a-124">它还允许用户使用 WCF 服务自动主机 （wcfSvcHost.exe），而无需授予管理员权限。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="2fe5a-125">您可以使用 Windows Vista 中的 Netsh.exe 工具在提升的管理员帐户下修改访问权限。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-125">You can modify access using the Netsh.exe tool in Windows Vista under the elevated administrator account.</span></span> <span data-ttu-id="2fe5a-126">下面是使用 Netsh.exe 的示例。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="2fe5a-127">有关 Netsh.exe 的详细信息，请参阅[如何使用 Netsh.exe 工具和命令行开关](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="2fe5a-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe5a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fe5a-128">See also</span></span>

- [<span data-ttu-id="2fe5a-129">WCF Visual Studio 模板</span><span class="sxs-lookup"><span data-stu-id="2fe5a-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="2fe5a-130">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="2fe5a-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="2fe5a-131">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="2fe5a-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
