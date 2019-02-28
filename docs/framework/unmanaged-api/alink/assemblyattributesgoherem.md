---
title: AssemblyAttributesGoHereM 类 (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
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
ms.openlocfilehash: 69167fda194e9d916f44751fd1f9dcee92822377
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972375"
---
# <a name="assemblyattributesgoherem-class"></a><span data-ttu-id="7f306-102">AssemblyAttributesGoHereM 类</span><span class="sxs-lookup"><span data-stu-id="7f306-102">AssemblyAttributesGoHereM Class</span></span>

<span data-ttu-id="7f306-103">由 ALink 用作占位符以存储有关自定义特性的信息。</span><span class="sxs-lookup"><span data-stu-id="7f306-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f306-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f306-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a><span data-ttu-id="7f306-105">备注</span><span class="sxs-lookup"><span data-stu-id="7f306-105">Remarks</span></span>

<span data-ttu-id="7f306-106">对此类型的引用可能被嵌入网络模块内，模块的源包含程序集自定义属性。</span><span class="sxs-lookup"><span data-stu-id="7f306-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="7f306-107">当从一个或多个包含对这些类型的引用的网络模块生成程序集清单时，ALink 将使用附加到这些引用的信息来发出实际的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="7f306-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="7f306-108">因此，此类型永远不会被实例化，而且对它的引用仅用作生成过程的一部分，在最终的程序集中不具有任何用途。</span><span class="sxs-lookup"><span data-stu-id="7f306-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="7f306-109">对此类型的引用指示了不与安全性相关但有多用途的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="7f306-109">References to this type indicate custom attributes that are not security related but are multiple-use.</span></span>

<span data-ttu-id="7f306-110">这些类型标记为"内部".NET Framework 中，并且位于<xref:System.Runtime.CompilerServices>命名空间。</span><span class="sxs-lookup"><span data-stu-id="7f306-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f306-111">要求</span><span class="sxs-lookup"><span data-stu-id="7f306-111">Requirements</span></span>

<span data-ttu-id="7f306-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="7f306-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="7f306-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f306-113">See also</span></span>

- [<span data-ttu-id="7f306-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="7f306-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="7f306-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="7f306-115">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
- [<span data-ttu-id="7f306-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="7f306-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
