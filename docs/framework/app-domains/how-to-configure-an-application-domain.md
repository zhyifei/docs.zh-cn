---
title: "如何：配置应用程序域"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79a05be9b3ddb9ca8aaabe13165efc5d851125a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="4a46b-102">如何：配置应用程序域</span><span class="sxs-lookup"><span data-stu-id="4a46b-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="4a46b-103">可以使用 <xref:System.AppDomainSetup> 类为新应用程序域提供含配置信息的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="4a46b-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="4a46b-104">创建自己的应用程序域时，最重要的属性是 <xref:System.AppDomainSetup.ApplicationBase%2A>。</span><span class="sxs-lookup"><span data-stu-id="4a46b-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="4a46b-105">其他 AppDomainSetup 属性主要由运行时宿主用于配置特殊的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="4a46b-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="4a46b-106">ApplicationBase 属性定义应用程序的根目录。</span><span class="sxs-lookup"><span data-stu-id="4a46b-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="4a46b-107">当运行时需要满足类型请求时，它会在 ApplicationBase 属性指定的目录中探测包含该类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="4a46b-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a46b-108">新的应用程序域只继承创建者的 ApplicationBase 属性。</span><span class="sxs-lookup"><span data-stu-id="4a46b-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="4a46b-109">以下示例创建 AppDomainSetup 类的实例，使用此类创建新的应用程序域，将信息写入控制台，然后卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="4a46b-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a46b-110">示例</span><span class="sxs-lookup"><span data-stu-id="4a46b-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4a46b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a46b-111">See Also</span></span>  
 [<span data-ttu-id="4a46b-112">对应用程序域进行编程</span><span class="sxs-lookup"><span data-stu-id="4a46b-112">Programming with Application Domains</span></span>](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="4a46b-113">使用应用程序域</span><span class="sxs-lookup"><span data-stu-id="4a46b-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
