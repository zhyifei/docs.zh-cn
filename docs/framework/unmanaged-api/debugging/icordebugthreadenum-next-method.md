---
title: ICorDebugThreadEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: 0c455706b0d644d2444e9fbdf49c5a5d4f5295a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122392"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="885cf-102">ICorDebugThreadEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="885cf-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="885cf-103">从当前位置开始，获取枚举中指定的 ICorDebugThread 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="885cf-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="885cf-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="885cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="885cf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="885cf-106">中要检索的 `ICorDebugThread` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="885cf-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="885cf-107">弄指针的数组，其中每个都指向表示线程的 `ICorDebugThread` 对象。</span><span class="sxs-lookup"><span data-stu-id="885cf-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="885cf-108">弄一个指针，指向实际返回的 `ICorDebugThread` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="885cf-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="885cf-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="885cf-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="885cf-110">要求</span><span class="sxs-lookup"><span data-stu-id="885cf-110">Requirements</span></span>  
 <span data-ttu-id="885cf-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="885cf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="885cf-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="885cf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="885cf-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="885cf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="885cf-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="885cf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
