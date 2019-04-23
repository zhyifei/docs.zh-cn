---
title: 如何：加载和卸载程序集 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
ms.openlocfilehash: efd8ddbe45323e1f80cec54379d61b5aa8a435cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297378"
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a><span data-ttu-id="bed85-102">如何：加载和卸载程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bed85-102">How to: Load and Unload Assemblies (Visual Basic)</span></span>
<span data-ttu-id="bed85-103">在生成时自动加载程序所引用的程序集，但也可以在运行时将特定的程序集加载到当前的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="bed85-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="bed85-104">有关详细信息，请参阅[如何：将程序集加载到应用程序域中](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="bed85-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="bed85-105">在没有卸载所有包含单个程序集的应用程序域之前，无法卸载此程序集。</span><span class="sxs-lookup"><span data-stu-id="bed85-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="bed85-106">即使程序集不在范围之内，在卸载包含它的所有应用程序域之前，实际的程序集文件都将保持加载状态。</span><span class="sxs-lookup"><span data-stu-id="bed85-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="bed85-107">如果想要卸载某些程序集而不是其他程序集，请考虑创建一个新的应用程序域，在此域中执行代码，然后卸载此应用程序域。</span><span class="sxs-lookup"><span data-stu-id="bed85-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="bed85-108">有关详细信息，请参阅[如何：卸载应用程序域](../../../../framework/app-domains/how-to-unload-an-application-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="bed85-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="bed85-109">将程序集加载到应用程序域中</span><span class="sxs-lookup"><span data-stu-id="bed85-109">To load an assembly into an application domain</span></span>  
  
1. <span data-ttu-id="bed85-110">使用 <xref:System.AppDomain> 和 <xref:System.Reflection> 类中包含的几种加载方法中的一种。</span><span class="sxs-lookup"><span data-stu-id="bed85-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="bed85-111">有关详细信息，请参阅[如何：将程序集加载到应用程序域中](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="bed85-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="bed85-112">卸载应用程序域</span><span class="sxs-lookup"><span data-stu-id="bed85-112">To unload an application domain</span></span>  
  
1. <span data-ttu-id="bed85-113">在没有卸载所有包含单个程序集的应用程序域之前，无法卸载此程序集。</span><span class="sxs-lookup"><span data-stu-id="bed85-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="bed85-114">使用 <xref:System.AppDomain> 中的 `Unload` 方法卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="bed85-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="bed85-115">有关详细信息，请参阅[如何：卸载应用程序域](../../../../framework/app-domains/how-to-unload-an-application-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="bed85-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed85-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bed85-116">See also</span></span>

- [<span data-ttu-id="bed85-117">编程概念</span><span class="sxs-lookup"><span data-stu-id="bed85-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="bed85-118">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="bed85-118">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="bed85-119">如何：将程序集加载到应用程序域中</span><span class="sxs-lookup"><span data-stu-id="bed85-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
