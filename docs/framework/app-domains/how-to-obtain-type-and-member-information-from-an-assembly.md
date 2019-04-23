---
title: 如何：从程序集获得类型和成员信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f9d01715a9635b276ca87d94082bb4d3820084e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138874"
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a><span data-ttu-id="5f5cf-102">如何：从程序集获得类型和成员信息</span><span class="sxs-lookup"><span data-stu-id="5f5cf-102">How to: Obtain Type and Member Information from an Assembly</span></span>
<span data-ttu-id="5f5cf-103"><xref:System.Reflection> 命名空间包含许多从程序集中获取信息的方法。</span><span class="sxs-lookup"><span data-stu-id="5f5cf-103">The <xref:System.Reflection> namespace contains many methods for obtaining information from an assembly.</span></span> <span data-ttu-id="5f5cf-104">本部分介绍其中的一种方法。</span><span class="sxs-lookup"><span data-stu-id="5f5cf-104">This section demonstrates one of these methods.</span></span> <span data-ttu-id="5f5cf-105">有关其他信息，请参阅[反射概述](../../../docs/framework/reflection-and-codedom/reflection.md)。</span><span class="sxs-lookup"><span data-stu-id="5f5cf-105">For additional information, see [Reflection Overview](../../../docs/framework/reflection-and-codedom/reflection.md).</span></span>  
  
 <span data-ttu-id="5f5cf-106">下例演示从程序集获取类型和成员信息。</span><span class="sxs-lookup"><span data-stu-id="5f5cf-106">The following example obtains type and member information from an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f5cf-107">示例</span><span class="sxs-lookup"><span data-stu-id="5f5cf-107">Example</span></span>  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="5f5cf-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f5cf-108">See also</span></span>

- [<span data-ttu-id="5f5cf-109">对应用程序域进行编程</span><span class="sxs-lookup"><span data-stu-id="5f5cf-109">Programming with Application Domains</span></span>](./application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="5f5cf-110">反射</span><span class="sxs-lookup"><span data-stu-id="5f5cf-110">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="5f5cf-111">使用应用程序域</span><span class="sxs-lookup"><span data-stu-id="5f5cf-111">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
