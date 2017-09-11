---
title: "如何︰ 加载和卸载程序集 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2e38be72bb58573b532fa42a569563df0be8301d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a><span data-ttu-id="fcc9e-102">如何︰ 加载和卸载程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fcc9e-102">How to: Load and Unload Assemblies (Visual Basic)</span></span>
<span data-ttu-id="fcc9e-103">由你的程序引用的程序集将自动加载在生成时，但也可以将特定的程序集加载到当前的应用程序域在运行时。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="fcc9e-104">有关详细信息，请参阅[如何︰ 将程序集加载到应用程序域](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-104">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
 <span data-ttu-id="fcc9e-105">没有办法无需卸载所有包含它的应用程序域卸载单个程序集。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="fcc9e-106">即使该程序集都超出范围，实际的程序集文件将保持被加载，直到包含它的所有应用程序域都会被卸载。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="fcc9e-107">如果您想要卸载某些程序集而不是其他卸载，请考虑创建一个新的应用程序域，该域中，在中执行代码然后卸载该应用程序域。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="fcc9e-108">有关详细信息，请参阅[如何︰ 卸载应用程序域](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192)。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-108">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="fcc9e-109">将程序集加载到应用程序域</span><span class="sxs-lookup"><span data-stu-id="fcc9e-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="fcc9e-110">使用多个类<xref:System.AppDomain>和<xref:System.Reflection>。</xref:System.Reflection></xref:System.AppDomain>中包含的 load 方法</span><span class="sxs-lookup"><span data-stu-id="fcc9e-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="fcc9e-111">有关详细信息，请参阅[如何︰ 将程序集加载到应用程序域](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-111">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="fcc9e-112">若要卸载的应用程序域</span><span class="sxs-lookup"><span data-stu-id="fcc9e-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="fcc9e-113">没有办法无需卸载所有包含它的应用程序域卸载单个程序集。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="fcc9e-114">使用`Unload`方法从<xref:System.AppDomain>卸载应用程序域。</xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="fcc9e-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="fcc9e-115">有关详细信息，请参阅[如何︰ 卸载应用程序域](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192)。</span><span class="sxs-lookup"><span data-stu-id="fcc9e-115">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc9e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcc9e-116">See Also</span></span>  
 <span data-ttu-id="fcc9e-117">[编程概念](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="fcc9e-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="fcc9e-118"> [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="fcc9e-118"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="fcc9e-119"> [如何︰ 将程序集加载到应用程序域](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span><span class="sxs-lookup"><span data-stu-id="fcc9e-119"> [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span></span>
