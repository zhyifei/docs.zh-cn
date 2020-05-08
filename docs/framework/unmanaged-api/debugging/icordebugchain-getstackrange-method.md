---
title: ICorDebugChain::GetStackRange 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 40ecc183c32500ad9e88ceb1bfc0528d717430e8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894452"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="bb2dc-102">ICorDebugChain::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="bb2dc-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="bb2dc-103">获取此链的堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="bb2dc-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb2dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb2dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb2dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb2dc-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="bb2dc-106">弄一个指针，指向`CORDB_ADDRESS`作为堆栈段起始地址的值。</span><span class="sxs-lookup"><span data-stu-id="bb2dc-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="bb2dc-107">弄一个指针，指向`CORDB_ADDRESS`作为堆栈段结束地址的值。</span><span class="sxs-lookup"><span data-stu-id="bb2dc-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb2dc-108">备注</span><span class="sxs-lookup"><span data-stu-id="bb2dc-108">Remarks</span></span>  
 <span data-ttu-id="bb2dc-109">数值范围仅用于比较堆栈帧位置。</span><span class="sxs-lookup"><span data-stu-id="bb2dc-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="bb2dc-110">您无法对堆栈上实际存储的内容作出任何假设。</span><span class="sxs-lookup"><span data-stu-id="bb2dc-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb2dc-111">要求</span><span class="sxs-lookup"><span data-stu-id="bb2dc-111">Requirements</span></span>  
 <span data-ttu-id="bb2dc-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb2dc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb2dc-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb2dc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb2dc-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb2dc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb2dc-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb2dc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
