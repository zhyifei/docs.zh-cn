---
title: AssemblyAttributesGoHereM
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHereM
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 075f0ce7001573bb4e61a3e059e699d15275ea0b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="assemblyattributesgoherem"></a><span data-ttu-id="dcf66-102">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="dcf66-102">AssemblyAttributesGoHereM</span></span>
<span data-ttu-id="dcf66-103">由 ALink 用作占位符以存储有关自定义特性的信息。</span><span class="sxs-lookup"><span data-stu-id="dcf66-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf66-104">语法</span><span class="sxs-lookup"><span data-stu-id="dcf66-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHereM  
```  
  
## <a name="remarks"></a><span data-ttu-id="dcf66-105">备注</span><span class="sxs-lookup"><span data-stu-id="dcf66-105">Remarks</span></span>  
 <span data-ttu-id="dcf66-106">对此类型的引用可能被嵌入网络模块内，模块的源包含程序集自定义属性。</span><span class="sxs-lookup"><span data-stu-id="dcf66-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="dcf66-107">当从一个或多个包含对这些类型的引用的网络模块生成程序集清单时，ALink 将使用附加到这些引用的信息来发出实际的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="dcf66-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="dcf66-108">因此，此类型永远不会被实例化，而且对它的引用仅用作生成过程的一部分，在最终的程序集中不具有任何用途。</span><span class="sxs-lookup"><span data-stu-id="dcf66-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="dcf66-109">对此类型的引用指示了不与安全性相关但有多用途的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="dcf66-109">References to this type indicate custom attributes that are not security related but are multiple-use.</span></span>  
  
 <span data-ttu-id="dcf66-110">这些类型在 .NET Framework 中标记为“内部的”，并位于 <xref:System.Runtime.CompilerServices>。</span><span class="sxs-lookup"><span data-stu-id="dcf66-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf66-111">要求</span><span class="sxs-lookup"><span data-stu-id="dcf66-111">Requirements</span></span>  
 <span data-ttu-id="dcf66-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="dcf66-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf66-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcf66-113">See Also</span></span>  
 [<span data-ttu-id="dcf66-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="dcf66-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)  
 [<span data-ttu-id="dcf66-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="dcf66-115">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)  
 [<span data-ttu-id="dcf66-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="dcf66-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
