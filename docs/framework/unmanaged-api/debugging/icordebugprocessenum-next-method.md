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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c298107983f4835569cfee7503537537ad11a165
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782989"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="19567-102">ICorDebugProcessEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="19567-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="19567-103">从当前位置开始枚举中获取指定的数量的 ICorDebugProcess 实例。</span><span class="sxs-lookup"><span data-stu-id="19567-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19567-104">语法</span><span class="sxs-lookup"><span data-stu-id="19567-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19567-105">参数</span><span class="sxs-lookup"><span data-stu-id="19567-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="19567-106">[in]数`ICorDebugProcess`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="19567-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processess`  
 <span data-ttu-id="19567-107">[out]一个指针，其中每个指向数组`ICorDebugProcess`表示进程的对象。</span><span class="sxs-lookup"><span data-stu-id="19567-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="19567-108">[out]指向数`ICorDebugProcess`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="19567-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="19567-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="19567-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19567-110">要求</span><span class="sxs-lookup"><span data-stu-id="19567-110">Requirements</span></span>  
 <span data-ttu-id="19567-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19567-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19567-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19567-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19567-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19567-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19567-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19567-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
