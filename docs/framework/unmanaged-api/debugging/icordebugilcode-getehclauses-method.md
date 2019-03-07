---
title: ICorDebugILCode::GetEHClauses 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60d9ae1abc97d348dced9e4a21236c70658a9141
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488131"
---
# <a name="icordebugilcodegetehclauses-method"></a><span data-ttu-id="903a0-102">ICorDebugILCode::GetEHClauses 方法</span><span class="sxs-lookup"><span data-stu-id="903a0-102">ICorDebugILCode::GetEHClauses Method</span></span>
<span data-ttu-id="903a0-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="903a0-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="903a0-104">返回指向为此中间语言 (IL) 定义的异常处理 (EH) 子句列表的指针。</span><span class="sxs-lookup"><span data-stu-id="903a0-104">Returns a pointer to a list of exception handling (EH) clauses that are defined for this intermediate language (IL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903a0-105">语法</span><span class="sxs-lookup"><span data-stu-id="903a0-105">Syntax</span></span>  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="903a0-106">参数</span><span class="sxs-lookup"><span data-stu-id="903a0-106">Parameters</span></span>  
 `cClauses`  
 <span data-ttu-id="903a0-107">[in] `clauses` 数组的存储容量。</span><span class="sxs-lookup"><span data-stu-id="903a0-107">[in] The storage capacity of the `clauses` array.</span></span> <span data-ttu-id="903a0-108">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="903a0-108">See the Remarks section for more information.</span></span>  
  
 `pcClauses`  
 <span data-ttu-id="903a0-109">[out] 有关哪些信息写入了 `clauses` 数组的子句数。</span><span class="sxs-lookup"><span data-stu-id="903a0-109">[out] The number of clauses about which information is written to the `clauses` array.</span></span>  
  
 <span data-ttu-id="903a0-110">子句</span><span class="sxs-lookup"><span data-stu-id="903a0-110">clauses</span></span>  
 <span data-ttu-id="903a0-111">[out]一个数组[CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)包含异常处理子句为此 IL 定义的信息的对象。</span><span class="sxs-lookup"><span data-stu-id="903a0-111">[out] An array of [CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) objects that contain information on exception handling clauses defined for this IL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="903a0-112">备注</span><span class="sxs-lookup"><span data-stu-id="903a0-112">Remarks</span></span>  
 <span data-ttu-id="903a0-113">如果`cClauses`为 0 和`pcClauses`为非**null**，`pcClauses`设为可用的异常处理子句数。</span><span class="sxs-lookup"><span data-stu-id="903a0-113">If `cClauses` is 0 and `pcClauses` is non-**null**, `pcClauses` is set to the number of available exception handling clauses.</span></span> <span data-ttu-id="903a0-114">如果 `clauses``cClauses` 为非零，则它表示  数组的存储容量。</span><span class="sxs-lookup"><span data-stu-id="903a0-114">If `cClauses` is non-zero, it represents the storage capacity of the `clauses` array.</span></span> <span data-ttu-id="903a0-115">当该方法返回时，`clauses` 将包含最大的 `cClauses` 项，并且 `pcClauses` 将设置为实际写入 `clauses` 数组的子句数。</span><span class="sxs-lookup"><span data-stu-id="903a0-115">When the method returns, `clauses` contains a maximum of `cClauses` items, and `pcClauses` is set to the number of clauses actually written to the `clauses` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="903a0-116">要求</span><span class="sxs-lookup"><span data-stu-id="903a0-116">Requirements</span></span>  
 <span data-ttu-id="903a0-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="903a0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903a0-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="903a0-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="903a0-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="903a0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="903a0-120">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="903a0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903a0-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="903a0-121">See also</span></span>
- [<span data-ttu-id="903a0-122">ICorDebugILCode 接口</span><span class="sxs-lookup"><span data-stu-id="903a0-122">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="903a0-123">CorDebugEHClause 结构</span><span class="sxs-lookup"><span data-stu-id="903a0-123">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)
- [<span data-ttu-id="903a0-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="903a0-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
