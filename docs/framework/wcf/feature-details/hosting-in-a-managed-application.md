---
title: 在托管应用程序中承载
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 1895f6622f7c528979badd741f5994970bbd1a8c
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169794"
---
# <a name="hosting-in-a-managed-application"></a><span data-ttu-id="4649f-102">在托管应用程序中承载</span><span class="sxs-lookup"><span data-stu-id="4649f-102">Hosting in a Managed Application</span></span>
<span data-ttu-id="4649f-103">可以在任何.NET Framework 应用程序中承载 Windows Communication Foundation (WCF) 服务。</span><span class="sxs-lookup"><span data-stu-id="4649f-103">Windows Communication Foundation (WCF) services can be hosted in any .NET Framework application.</span></span> <span data-ttu-id="4649f-104">自承载服务是最灵活的宿主选项，因为此服务部署所需要的基础结构最少。</span><span class="sxs-lookup"><span data-stu-id="4649f-104">Self-hosting services is the most flexible hosting option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="4649f-105">但是，它也是最不可靠宿主选项，因为托管应用程序不提供的高级宿主和管理功能，如 Internet 信息服务 (IIS) 和 Windows 服务在 WCF 中，其他托管选项。</span><span class="sxs-lookup"><span data-stu-id="4649f-105">However, it is also the least robust hosting option, because managed applications do not provide the advanced hosting and management features of other hosting options in WCF, such as Internet Information Services (IIS) and Windows services.</span></span>  
  
 <span data-ttu-id="4649f-106">若要创建自承载服务，请创建并打开 <xref:System.ServiceModel.ServiceHost>的实例以启动侦听消息的服务。</span><span class="sxs-lookup"><span data-stu-id="4649f-106">To create a self-hosted service, create and open an instance of the <xref:System.ServiceModel.ServiceHost>, which starts a service listening for messages.</span></span> <span data-ttu-id="4649f-107">有关详细信息，请参阅[如何：承载于托管应用程序的 WCF 服务](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4649f-107">For more information, see [How to: Host a WCF Service in a Managed Application](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="4649f-108">有关如何定义协定、 实现协定，和托管应用程序内托管服务的完整示例请参阅[入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)并[自承载](../../../../docs/framework/wcf/samples/self-host.md)。</span><span class="sxs-lookup"><span data-stu-id="4649f-108">For a complete example on how to define a contract, implement the contract, and host a service inside of a managed application see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md) and the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md).</span></span>  
  
 <span data-ttu-id="4649f-109">以下各部分描述了使用此宿主选项的常见情况。</span><span class="sxs-lookup"><span data-stu-id="4649f-109">The following sections describe common scenarios that use this hosting option.</span></span>  
  
## <a name="console-applications"></a><span data-ttu-id="4649f-110">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="4649f-110">Console Applications</span></span>  
 <span data-ttu-id="4649f-111">自承载支持的常见方案是控制台应用程序内运行的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="4649f-111">Common scenarios that self-hosting enables are WCF services running inside console applications.</span></span> <span data-ttu-id="4649f-112">承载 WCF 服务中的控制台应用程序服务在开发阶段是通常很有用。</span><span class="sxs-lookup"><span data-stu-id="4649f-112">Hosting a WCF service inside a console application is typically useful during the development phase of the service.</span></span> <span data-ttu-id="4649f-113">这使服务变得容易调试，从中跟踪信息以查明应用程序内发生的情况变得更加方便，以及通过将其复制到新的位置进行来回移动变得更加轻松。</span><span class="sxs-lookup"><span data-stu-id="4649f-113">This makes them easy to debug, easy to get trace information from to find out what is happening inside of the application, and easy to move around by copying them to new locations.</span></span>  
  
## <a name="rich-client-applications"></a><span data-ttu-id="4649f-114">胖客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="4649f-114">Rich Client Applications</span></span>  
 <span data-ttu-id="4649f-115">自承载支持是丰富的客户端应用程序，如基于 Windows Presentation Foundation (WPF) 或 Windows 窗体 (WinForms) 其他常见方案。</span><span class="sxs-lookup"><span data-stu-id="4649f-115">Other common scenarios that self-hosting enables are rich client applications, such as those based on Windows Presentation Foundation (WPF) or Windows Forms (WinForms).</span></span> <span data-ttu-id="4649f-116">此宿主选项还便于丰富的客户端应用程序，如 WPF 和 WinForms 应用程序，与外界进行通信。</span><span class="sxs-lookup"><span data-stu-id="4649f-116">This hosting option also makes it easy for rich client applications, such as WPF and WinForms applications, to communicate with the outside world.</span></span> <span data-ttu-id="4649f-117">例如，为其用户界面中使用 WPF 和也承载 WCF 服务，允许其他客户端连接到它并共享信息的对等协作客户端。</span><span class="sxs-lookup"><span data-stu-id="4649f-117">For example, a peer-to-peer collaboration client that uses WPF for its user interface and also hosts a WCF service that allows other clients to connect to it and share information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4649f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4649f-118">See also</span></span>

- [<span data-ttu-id="4649f-119">托管服务</span><span class="sxs-lookup"><span data-stu-id="4649f-119">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="4649f-120">入门教程</span><span class="sxs-lookup"><span data-stu-id="4649f-120">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
