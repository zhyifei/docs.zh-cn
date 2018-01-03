---
title: AssemblyAttributesGoHereS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyAttributesGoHereS
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac8f25632521f2e8abe5209608e42632293feb4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="6681a-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="6681a-102">AssemblyAttributesGoHereS</span></span>
<span data-ttu-id="6681a-103">由 ALink 用作占位符以存储有关自定义特性的信息。</span><span class="sxs-lookup"><span data-stu-id="6681a-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6681a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6681a-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHereS  
```  
  
## <a name="remarks"></a><span data-ttu-id="6681a-105">备注</span><span class="sxs-lookup"><span data-stu-id="6681a-105">Remarks</span></span>  
 <span data-ttu-id="6681a-106">对此类型的引用可能被嵌入网络模块内，模块的源包含程序集自定义属性。</span><span class="sxs-lookup"><span data-stu-id="6681a-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="6681a-107">当从一个或多个包含对这些类型的引用的网络模块生成程序集清单时，ALink 将使用附加到这些引用的信息来发出实际的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="6681a-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="6681a-108">因此，此类型永远不会被实例化，而且对它的引用仅用作生成过程的一部分，在最终的程序集中不具有任何用途。</span><span class="sxs-lookup"><span data-stu-id="6681a-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="6681a-109">对此类型的引用指示了安全性相关的和非多用途的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="6681a-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="6681a-110">这些类型在 .NET Framework 中标记为“内部的”，并位于 <xref:System.Runtime.CompilerServices>。</span><span class="sxs-lookup"><span data-stu-id="6681a-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6681a-111">惠?</span><span class="sxs-lookup"><span data-stu-id="6681a-111">Requirements</span></span>  
 <span data-ttu-id="6681a-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="6681a-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6681a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6681a-113">See Also</span></span>  
 [<span data-ttu-id="6681a-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="6681a-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)  
 [<span data-ttu-id="6681a-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="6681a-115">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="6681a-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="6681a-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
