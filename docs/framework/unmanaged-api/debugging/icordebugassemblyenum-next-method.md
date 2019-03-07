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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25861b2635605042acc1bf81f3f7a4739e678522
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493105"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="ffb7b-102">ICorDebugAssemblyEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="ffb7b-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="ffb7b-103">从集合中，从当前光标位置开始获取指定的数目的程序集。</span><span class="sxs-lookup"><span data-stu-id="ffb7b-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffb7b-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffb7b-105">参数</span><span class="sxs-lookup"><span data-stu-id="ffb7b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ffb7b-106">[in]要检索的程序集的数量。</span><span class="sxs-lookup"><span data-stu-id="ffb7b-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="ffb7b-107">[out]一个指针数组，其中每个指向一个 icor 调试程序集对象，表示程序集。</span><span class="sxs-lookup"><span data-stu-id="ffb7b-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ffb7b-108">[out]一个指向实际返回的程序集的数量。</span><span class="sxs-lookup"><span data-stu-id="ffb7b-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="ffb7b-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="ffb7b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffb7b-110">要求</span><span class="sxs-lookup"><span data-stu-id="ffb7b-110">Requirements</span></span>  
 <span data-ttu-id="ffb7b-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffb7b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffb7b-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffb7b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffb7b-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffb7b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffb7b-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffb7b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
