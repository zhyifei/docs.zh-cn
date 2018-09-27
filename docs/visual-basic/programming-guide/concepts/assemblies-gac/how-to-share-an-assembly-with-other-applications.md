---
title: 如何： 与其他应用程序 (Visual Basic) 共享程序集
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 3d29a3558a64c02fc8c59035f2fee5c64c4a776f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47235239"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="0126c-102">如何： 与其他应用程序 (Visual Basic) 共享程序集</span><span class="sxs-lookup"><span data-stu-id="0126c-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="0126c-103">程序集可以是私有或共享程序集：默认情况下，大多数简单程序都包含一个私有程序集，因为它们并不打算由其他应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="0126c-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="0126c-104">若要与其他应用程序共享程序集，必须将它放置在[全局程序集缓存](../../../../framework/app-domains/gac.md) (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="0126c-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="0126c-105">共享程序集</span><span class="sxs-lookup"><span data-stu-id="0126c-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="0126c-106">创建程序集。</span><span class="sxs-lookup"><span data-stu-id="0126c-106">Create your assembly.</span></span> <span data-ttu-id="0126c-107">有关详细信息，请参阅[创建程序集](../../../../framework/app-domains/create-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="0126c-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="0126c-108">向程序集分配强名称。</span><span class="sxs-lookup"><span data-stu-id="0126c-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="0126c-109">有关详细信息，请参阅[如何：使用强名称为程序集签名](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)。</span><span class="sxs-lookup"><span data-stu-id="0126c-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="0126c-110">将版本信息分配给程序集。</span><span class="sxs-lookup"><span data-stu-id="0126c-110">Assign version information to your assembly.</span></span> <span data-ttu-id="0126c-111">有关详细信息，请参阅[程序集版本控制](../../../../framework/app-domains/assembly-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="0126c-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="0126c-112">将程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="0126c-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="0126c-113">有关详细信息，请参阅[如何：将程序集安装到全局程序集缓存](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md)。</span><span class="sxs-lookup"><span data-stu-id="0126c-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="0126c-114">从其他应用程序访问该程序集中包含的类型。</span><span class="sxs-lookup"><span data-stu-id="0126c-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="0126c-115">有关详细信息，请参阅[如何：引用具有强名称的程序集](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md)。</span><span class="sxs-lookup"><span data-stu-id="0126c-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0126c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0126c-116">See also</span></span>

- [<span data-ttu-id="0126c-117">编程概念</span><span class="sxs-lookup"><span data-stu-id="0126c-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="0126c-118">程序集和全局程序集缓存 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0126c-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="0126c-119">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="0126c-119">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
