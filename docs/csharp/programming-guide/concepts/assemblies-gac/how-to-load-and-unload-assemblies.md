---
title: 如何：加载和卸载程序集 (C#)
ms.date: 07/20/2015
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: 2934ff07026d520f52309e50eb7da24731608292
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259644"
---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="f7eae-102">如何：加载和卸载程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="f7eae-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="f7eae-103">在生成时自动加载程序所引用的程序集，但也可以在运行时将特定的程序集加载到当前的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f7eae-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="f7eae-104">有关详细信息，请参阅 [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)（如何：将程序集加载到应用程序域中）。</span><span class="sxs-lookup"><span data-stu-id="f7eae-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="f7eae-105">在没有卸载所有包含单个程序集的应用程序域之前，无法卸载此程序集。</span><span class="sxs-lookup"><span data-stu-id="f7eae-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="f7eae-106">即使程序集不在范围之内，在卸载包含它的所有应用程序域之前，实际的程序集文件都将保持加载状态。</span><span class="sxs-lookup"><span data-stu-id="f7eae-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="f7eae-107">如果想要卸载某些程序集而不是其他程序集，请考虑创建一个新的应用程序域，在此域中执行代码，然后卸载此应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f7eae-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="f7eae-108">有关详细信息，请参阅 [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md)（如何：卸载应用程序域）。</span><span class="sxs-lookup"><span data-stu-id="f7eae-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="f7eae-109">将程序集加载到应用程序域中</span><span class="sxs-lookup"><span data-stu-id="f7eae-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="f7eae-110">使用 <xref:System.AppDomain> 和 <xref:System.Reflection> 类中包含的几种加载方法中的一种。</span><span class="sxs-lookup"><span data-stu-id="f7eae-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="f7eae-111">有关详细信息，请参阅 [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)（如何：将程序集加载到应用程序域中）。</span><span class="sxs-lookup"><span data-stu-id="f7eae-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="f7eae-112">卸载应用程序域</span><span class="sxs-lookup"><span data-stu-id="f7eae-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="f7eae-113">在没有卸载所有包含单个程序集的应用程序域之前，无法卸载此程序集。</span><span class="sxs-lookup"><span data-stu-id="f7eae-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="f7eae-114">使用 <xref:System.AppDomain> 中的 `Unload` 方法卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f7eae-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="f7eae-115">有关详细信息，请参阅 [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md)（如何：卸载应用程序域）。</span><span class="sxs-lookup"><span data-stu-id="f7eae-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7eae-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7eae-116">See Also</span></span>

- [<span data-ttu-id="f7eae-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f7eae-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f7eae-118">程序集和全局程序集缓存 (C#)</span><span class="sxs-lookup"><span data-stu-id="f7eae-118">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="f7eae-119">如何：将程序集加载到应用程序域中</span><span class="sxs-lookup"><span data-stu-id="f7eae-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
