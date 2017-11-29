---
title: "部署 WCF 库项目"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04567b0b06ef5c8f105e866e150bfaa221d64057
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="deploying-a-wcf-library-project"></a><span data-ttu-id="9a523-102">部署 WCF 库项目</span><span class="sxs-lookup"><span data-stu-id="9a523-102">Deploying a WCF Library Project</span></span>
<span data-ttu-id="9a523-103">本主题介绍如何部署 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="9a523-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Library Project.</span></span>  
  
## <a name="deploying-a-wcf-service-library"></a><span data-ttu-id="9a523-104">部署 WCF 服务库</span><span class="sxs-lookup"><span data-stu-id="9a523-104">Deploying a WCF Service Library</span></span>  
 <span data-ttu-id="9a523-105">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库是一个动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="9a523-105">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library is a dynamic-link library (DLL).</span></span> <span data-ttu-id="9a523-106">因此，它不能自己运行。</span><span class="sxs-lookup"><span data-stu-id="9a523-106">As such, it cannot be executed on its own.</span></span> <span data-ttu-id="9a523-107">必须将其部署到宿主环境中。</span><span class="sxs-lookup"><span data-stu-id="9a523-107">It needs to be deployed into a hosting environment.</span></span> <span data-ttu-id="9a523-108">有关此过程的详细信息，请参阅[托管和使用 WCF 服务](http://go.microsoft.com/fwlink/?LinkId=99932)。</span><span class="sxs-lookup"><span data-stu-id="9a523-108">For more information about this process, see [Hosting and Consuming WCF Services](http://go.microsoft.com/fwlink/?LinkId=99932).</span></span>  
  
 <span data-ttu-id="9a523-109">可以像部署任何其他 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务一样部署 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库。</span><span class="sxs-lookup"><span data-stu-id="9a523-109">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library can be deployed like any other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="9a523-110">但请注意，[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 不支持 DLL 的配置。</span><span class="sxs-lookup"><span data-stu-id="9a523-110">However, be aware that [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] does not support configuration for DLLs.</span></span> <span data-ttu-id="9a523-111"><xref:System.Configuration> 支持每个应用程序域一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="9a523-111"><xref:System.Configuration> supports one configuration file per app-domain.</span></span> <span data-ttu-id="9a523-112">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库项目通过在开发期间为库提供 App.config 文件来减少此限制。</span><span class="sxs-lookup"><span data-stu-id="9a523-112">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library project alleviates this limitation by providing an App.config file for the library during development.</span></span> <span data-ttu-id="9a523-113">但在部署之后不能识别 App.config 文件。</span><span class="sxs-lookup"><span data-stu-id="9a523-113">However, the App.config file is not recognized after deployment.</span></span>  
  
 <span data-ttu-id="9a523-114">必须将配置代码移动到宿主环境所识别的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="9a523-114">You have to move your configuration code into the configuration file recognized by your hosting environment.</span></span> <span data-ttu-id="9a523-115">对于自承载，您应将 App.config 文件的内容复制到宿主可执行文件的 App.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="9a523-115">For self-hosting, you should copy the contents of the App.config file into the App.config file of the hosting executable.</span></span> <span data-ttu-id="9a523-116">如果使用 IIS 承载服务，则应将 App.config 文件的内容复制到虚拟目录的 Web.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="9a523-116">If you use IIS to host your service, you should copy the contents of the App.config file into the Web.config file of the virtual directory.</span></span>
