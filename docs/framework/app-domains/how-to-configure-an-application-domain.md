---
title: 如何：配置应用程序域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 012f0220afa0e444d68af5998fb2492a03a371d8
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50183160"
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="8965c-102">如何：配置应用程序域</span><span class="sxs-lookup"><span data-stu-id="8965c-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="8965c-103">可以使用 <xref:System.AppDomainSetup> 类为新应用程序域提供含配置信息的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="8965c-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="8965c-104">创建自己的应用程序域时，最重要的属性是 <xref:System.AppDomainSetup.ApplicationBase%2A>。</span><span class="sxs-lookup"><span data-stu-id="8965c-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="8965c-105">其他 AppDomainSetup 属性主要由运行时宿主用于配置特殊的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="8965c-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="8965c-106">ApplicationBase 属性定义应用程序的根目录。</span><span class="sxs-lookup"><span data-stu-id="8965c-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="8965c-107">当运行时需要满足类型请求时，它会在 ApplicationBase 属性指定的目录中探测包含该类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="8965c-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8965c-108">新的应用程序域只继承创建者的 ApplicationBase 属性。</span><span class="sxs-lookup"><span data-stu-id="8965c-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="8965c-109">以下示例创建 AppDomainSetup 类的实例，使用此类创建新的应用程序域，将信息写入控制台，然后卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="8965c-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8965c-110">示例</span><span class="sxs-lookup"><span data-stu-id="8965c-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8965c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8965c-111">See Also</span></span>  
- [<span data-ttu-id="8965c-112">对应用程序域进行编程</span><span class="sxs-lookup"><span data-stu-id="8965c-112">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)  
- [<span data-ttu-id="8965c-113">使用应用程序域</span><span class="sxs-lookup"><span data-stu-id="8965c-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
