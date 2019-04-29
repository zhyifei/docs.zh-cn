---
title: AssemblyAttributesGoHereSM 类 (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereSM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b156ed9c318e71a408ea10f2744911a85faedc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790333"
---
# <a name="assemblyattributesgoheresm-class"></a><span data-ttu-id="c9cb3-102">AssemblyAttributesGoHereSM 类</span><span class="sxs-lookup"><span data-stu-id="c9cb3-102">AssemblyAttributesGoHereSM Class</span></span>

<span data-ttu-id="c9cb3-103">由 ALink 用作占位符以存储有关自定义特性的信息。</span><span class="sxs-lookup"><span data-stu-id="c9cb3-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9cb3-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9cb3-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereSM
```

## <a name="remarks"></a><span data-ttu-id="c9cb3-105">备注</span><span class="sxs-lookup"><span data-stu-id="c9cb3-105">Remarks</span></span>

<span data-ttu-id="c9cb3-106">对此类型的引用可能被嵌入网络模块内，模块的源包含程序集自定义属性。</span><span class="sxs-lookup"><span data-stu-id="c9cb3-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="c9cb3-107">当从一个或多个包含对这些类型的引用的网络模块生成程序集清单时，ALink 将使用附加到这些引用的信息来发出实际的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="c9cb3-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="c9cb3-108">因此，此类型永远不会被实例化，而且对它的引用仅用作生成过程的一部分，在最终的程序集中不具有任何用途。</span><span class="sxs-lookup"><span data-stu-id="c9cb3-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="c9cb3-109">对此类型的引用指示了安全性相关的多用途自定义属性。</span><span class="sxs-lookup"><span data-stu-id="c9cb3-109">References to this type indicate custom attributes that are security related and multiple-use.</span></span>

<span data-ttu-id="c9cb3-110">这些类型标记为"内部".NET Framework 中，并且位于<xref:System.Runtime.CompilerServices>命名空间。</span><span class="sxs-lookup"><span data-stu-id="c9cb3-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="c9cb3-111">要求</span><span class="sxs-lookup"><span data-stu-id="c9cb3-111">Requirements</span></span>

<span data-ttu-id="c9cb3-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="c9cb3-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="c9cb3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9cb3-113">See also</span></span>

- [<span data-ttu-id="c9cb3-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="c9cb3-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="c9cb3-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="c9cb3-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="c9cb3-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="c9cb3-116">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
