---
title: ICorDebugFrameEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be126e45d8428d8786e9aadf2195133d1957440
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754833"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="0d81c-102">ICorDebugFrameEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="0d81c-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="0d81c-103">获取指定的数量的 ICorDebugFrame 实例，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="0d81c-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d81c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d81c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d81c-105">参数</span><span class="sxs-lookup"><span data-stu-id="0d81c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0d81c-106">[in]数`ICorDebugFrame`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="0d81c-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="0d81c-107">[out]一个指针，其中每个指向数组`ICorDebugFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="0d81c-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0d81c-108">[out]指向数`ICorDebugFrame`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="0d81c-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="0d81c-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="0d81c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d81c-110">要求</span><span class="sxs-lookup"><span data-stu-id="0d81c-110">Requirements</span></span>  
 <span data-ttu-id="0d81c-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d81c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d81c-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d81c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d81c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d81c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d81c-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d81c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
