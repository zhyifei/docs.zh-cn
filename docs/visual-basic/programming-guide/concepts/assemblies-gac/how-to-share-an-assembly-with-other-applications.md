---
title: "如何︰ 与其他应用程序 (Visual Basic 中) 共享程序集 |Microsoft 文档"
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
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
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
ms.openlocfilehash: ceebb3934c269284db18c9ca8e561417eaf5baa1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="744c1-102">如何︰ 与其他应用程序 (Visual Basic 中) 共享程序集</span><span class="sxs-lookup"><span data-stu-id="744c1-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="744c1-103">程序集可以为专用或共享︰ 默认情况下，大多数简单的程序都包含一个私有程序集，因为不应将它们用于其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="744c1-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="744c1-104">为了与其他应用程序共享程序集，必须将它放置在[全局程序集缓存](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)(GAC 中)。</span><span class="sxs-lookup"><span data-stu-id="744c1-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="744c1-105">共享程序集</span><span class="sxs-lookup"><span data-stu-id="744c1-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="744c1-106">创建您的程序集。</span><span class="sxs-lookup"><span data-stu-id="744c1-106">Create your assembly.</span></span> <span data-ttu-id="744c1-107">有关详细信息，请参阅[创建程序集](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4)。</span><span class="sxs-lookup"><span data-stu-id="744c1-107">For more information, see [Creating Assemblies](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).</span></span>  
  
2.  <span data-ttu-id="744c1-108">为您的程序集分配强名称。</span><span class="sxs-lookup"><span data-stu-id="744c1-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="744c1-109">有关详细信息，请参阅[如何︰ 使用强名称为程序集签名](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67)。</span><span class="sxs-lookup"><span data-stu-id="744c1-109">For more information, see [How to: Sign an Assembly with a Strong Name](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).</span></span>  
  
3.  <span data-ttu-id="744c1-110">将版本信息分配给您的程序集。</span><span class="sxs-lookup"><span data-stu-id="744c1-110">Assign version information to your assembly.</span></span> <span data-ttu-id="744c1-111">有关详细信息，请参阅[程序集版本控制](https://msdn.microsoft.com/library/51ket42z)。</span><span class="sxs-lookup"><span data-stu-id="744c1-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="744c1-112">将您的程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="744c1-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="744c1-113">有关详细信息，请参阅[如何︰ 将程序集安装到全局程序集缓存](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743)。</span><span class="sxs-lookup"><span data-stu-id="744c1-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).</span></span>  
  
5.  <span data-ttu-id="744c1-114">访问包含从其他应用程序的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="744c1-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="744c1-115">有关详细信息，请参阅[如何︰ 引用具有强名称程序集](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813)。</span><span class="sxs-lookup"><span data-stu-id="744c1-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="744c1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="744c1-116">See Also</span></span>  
 <span data-ttu-id="744c1-117">[编程概念](../../../../visual-basic/programming-guide/concepts/index.md)
 [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="744c1-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)
 [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="744c1-118"> [使用程序集编程](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)</span><span class="sxs-lookup"><span data-stu-id="744c1-118"> [Programming with Assemblies](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)</span></span>
