---
title: IMethodMalloc::Alloc 方法
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a676989bdc6866f85fabe3e15b1e6b7b8b5a9a9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351250"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="beb4e-102">IMethodMalloc::Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="beb4e-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="beb4e-103">尝试为新的 Microsoft 中间语言 (MSIL) 函数主体分配指定的内存量。</span><span class="sxs-lookup"><span data-stu-id="beb4e-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="beb4e-104">语法</span><span class="sxs-lookup"><span data-stu-id="beb4e-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="beb4e-105">参数</span><span class="sxs-lookup"><span data-stu-id="beb4e-105">Parameters</span></span>

`cb`\
<span data-ttu-id="beb4e-106">[in]要为方法主体分配的字节数。</span><span class="sxs-lookup"><span data-stu-id="beb4e-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="beb4e-107">备注</span><span class="sxs-lookup"><span data-stu-id="beb4e-107">Remarks</span></span>

 <span data-ttu-id="beb4e-108">已分配的内存将大于与此分配器相关联的模块的基址的地址处开始。</span><span class="sxs-lookup"><span data-stu-id="beb4e-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="beb4e-109">换而言之，每个分配器创建特定的模块，并将尝试从其基址分配内存的正偏移位置。</span><span class="sxs-lookup"><span data-stu-id="beb4e-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="beb4e-110">如果`Alloc`无法分配请求的数目的字节大于该模块的基址的地址处返回 E_OUTOFMEMORY，而不考虑实际的可用内存空间量。</span><span class="sxs-lookup"><span data-stu-id="beb4e-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="beb4e-111">`Alloc`方法应结合使用[icorprofilerinfo:: Setilfunctionbody](icorprofilerinfo-setilfunctionbody-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="beb4e-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="beb4e-112">要求</span><span class="sxs-lookup"><span data-stu-id="beb4e-112">Requirements</span></span>
 <span data-ttu-id="beb4e-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="beb4e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="beb4e-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="beb4e-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="beb4e-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beb4e-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="beb4e-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb4e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="beb4e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="beb4e-117">See also</span></span>

- [<span data-ttu-id="beb4e-118">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="beb4e-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)