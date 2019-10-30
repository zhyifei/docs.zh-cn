---
title: ICorDebugAssemblyEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
ms.openlocfilehash: 86fa44b609b4b89cfaa28f0bfa7bbdce6217623f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122860"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="eee4a-102">ICorDebugAssemblyEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="eee4a-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="eee4a-103">从当前游标位置开始，从集合中获取指定数目的程序集。</span><span class="sxs-lookup"><span data-stu-id="eee4a-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee4a-104">语法</span><span class="sxs-lookup"><span data-stu-id="eee4a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eee4a-105">参数</span><span class="sxs-lookup"><span data-stu-id="eee4a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="eee4a-106">中要检索的程序集的数目。</span><span class="sxs-lookup"><span data-stu-id="eee4a-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="eee4a-107">弄指针的数组，其中每个都指向表示程序集的 ICorDebugAssembly 对象。</span><span class="sxs-lookup"><span data-stu-id="eee4a-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="eee4a-108">弄一个指针，指向实际返回的程序集的数目。</span><span class="sxs-lookup"><span data-stu-id="eee4a-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="eee4a-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="eee4a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eee4a-110">要求</span><span class="sxs-lookup"><span data-stu-id="eee4a-110">Requirements</span></span>  
 <span data-ttu-id="eee4a-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eee4a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eee4a-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eee4a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eee4a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eee4a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eee4a-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eee4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
