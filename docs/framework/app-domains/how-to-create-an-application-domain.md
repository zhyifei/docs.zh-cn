---
title: "如何：创建应用程序域"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 39d8db32f82827e76d9517d387e2fc001fc209aa
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="836c2-102">如何：创建应用程序域</span><span class="sxs-lookup"><span data-stu-id="836c2-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="836c2-103">需要应用程序域时，公共语言运行时主机会自动创建它们。</span><span class="sxs-lookup"><span data-stu-id="836c2-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="836c2-104">但是，可以创建自己的应用程序域并将其加载到需要亲自管理的程序集中。</span><span class="sxs-lookup"><span data-stu-id="836c2-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="836c2-105">也可以创建从中执行代码的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="836c2-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="836c2-106">使用 <xref:System.AppDomain?displayProperty=fullName> 类中某个重载的 CreateDomain 方法，创建新的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="836c2-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=fullName> class.</span></span> <span data-ttu-id="836c2-107">可以为应用程序域命名并按名称来引用应用程序域。</span><span class="sxs-lookup"><span data-stu-id="836c2-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="836c2-108">以下示例创建新的应用程序域，并为它指定名称 `MyDomain`，然后将主机域和新创建的子应用程序域的名称打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="836c2-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="836c2-109">示例</span><span class="sxs-lookup"><span data-stu-id="836c2-109">Example</span></span>  
 <span data-ttu-id="836c2-110">[!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)] [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)] [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="836c2-110">[!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)] [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)] [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836c2-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="836c2-111">See Also</span></span>  
 <span data-ttu-id="836c2-112">[对应用程序域进行编程](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="836c2-112">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 [<span data-ttu-id="836c2-113">使用应用程序域</span><span class="sxs-lookup"><span data-stu-id="836c2-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)

