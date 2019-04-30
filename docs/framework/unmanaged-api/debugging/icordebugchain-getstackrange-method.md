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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40927ac9469e4a2fb74fb550287130b9bb9f83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989451"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="7456d-102">ICorDebugChain::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="7456d-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="7456d-103">获取此链堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="7456d-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7456d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7456d-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7456d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7456d-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="7456d-106">[out]一个指向`CORDB_ADDRESS`堆栈段的起始地址的值。</span><span class="sxs-lookup"><span data-stu-id="7456d-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="7456d-107">[out]一个指向`CORDB_ADDRESS`是堆栈段的结束地址的值。</span><span class="sxs-lookup"><span data-stu-id="7456d-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7456d-108">备注</span><span class="sxs-lookup"><span data-stu-id="7456d-108">Remarks</span></span>  
 <span data-ttu-id="7456d-109">数值范围是仅对的堆栈帧位置比较有意义。</span><span class="sxs-lookup"><span data-stu-id="7456d-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="7456d-110">不能进行任何假设实际存储在堆栈上的内容。</span><span class="sxs-lookup"><span data-stu-id="7456d-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7456d-111">要求</span><span class="sxs-lookup"><span data-stu-id="7456d-111">Requirements</span></span>  
 <span data-ttu-id="7456d-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7456d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7456d-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7456d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7456d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7456d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7456d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7456d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
