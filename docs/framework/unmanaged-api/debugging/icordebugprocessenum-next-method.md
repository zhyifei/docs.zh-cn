---
title: ICorDebugProcessEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: 0666becb5a34688d3f4cf5bddd1e2fa71785b38a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139786"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="366a4-102">ICorDebugProcessEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="366a4-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="366a4-103">从当前位置开始，从枚举中获取指定数量的 ICorDebugProcess 实例。</span><span class="sxs-lookup"><span data-stu-id="366a4-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="366a4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="366a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="366a4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="366a4-106">中要检索的 `ICorDebugProcess` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="366a4-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="366a4-107">弄指针的数组，其中每个都指向表示进程的 `ICorDebugProcess` 对象。</span><span class="sxs-lookup"><span data-stu-id="366a4-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="366a4-108">弄一个指针，指向实际返回的 `ICorDebugProcess` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="366a4-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="366a4-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="366a4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="366a4-110">要求</span><span class="sxs-lookup"><span data-stu-id="366a4-110">Requirements</span></span>  
 <span data-ttu-id="366a4-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="366a4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="366a4-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="366a4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="366a4-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="366a4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="366a4-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="366a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
