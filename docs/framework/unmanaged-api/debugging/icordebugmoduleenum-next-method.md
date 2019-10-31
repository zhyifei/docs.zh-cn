---
title: ICorDebugModuleEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: 6c4262c18e4efcbbca1b3e2a327fec7d4b609a31
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096931"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="94aba-102">ICorDebugModuleEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="94aba-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="94aba-103">从当前位置开始，获取从枚举 `celt` 指定的 "ICorDebugModule" 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="94aba-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94aba-104">语法</span><span class="sxs-lookup"><span data-stu-id="94aba-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94aba-105">参数</span><span class="sxs-lookup"><span data-stu-id="94aba-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="94aba-106">中要检索的 `ICorDebugModule` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="94aba-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="94aba-107">弄指针的数组，其中每个都指向一个 `ICorDebugModule` 对象。</span><span class="sxs-lookup"><span data-stu-id="94aba-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="94aba-108">弄一个指针，指向实际返回的 `ICorDebugModule` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="94aba-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="94aba-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="94aba-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94aba-110">要求</span><span class="sxs-lookup"><span data-stu-id="94aba-110">Requirements</span></span>  
 <span data-ttu-id="94aba-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94aba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94aba-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94aba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94aba-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94aba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94aba-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94aba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94aba-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="94aba-115">See also</span></span>
