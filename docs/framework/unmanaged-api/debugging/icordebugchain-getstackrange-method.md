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
ms.openlocfilehash: 64e697323377d664b7b1e36bbf5931a44465cc51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178958"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="8ed0e-102">ICorDebugChain::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="8ed0e-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="8ed0e-103">获取此链的堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="8ed0e-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ed0e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ed0e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="8ed0e-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="8ed0e-106">[出]指向作为堆栈`CORDB_ADDRESS`段起始地址的值的指针。</span><span class="sxs-lookup"><span data-stu-id="8ed0e-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="8ed0e-107">[出]指向作为堆栈`CORDB_ADDRESS`段结束地址的值的指针。</span><span class="sxs-lookup"><span data-stu-id="8ed0e-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ed0e-108">备注</span><span class="sxs-lookup"><span data-stu-id="8ed0e-108">Remarks</span></span>  
 <span data-ttu-id="8ed0e-109">数值范围仅对堆栈帧位置的比较有意义。</span><span class="sxs-lookup"><span data-stu-id="8ed0e-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="8ed0e-110">您不能对堆栈中实际存储的内容进行任何假设。</span><span class="sxs-lookup"><span data-stu-id="8ed0e-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ed0e-111">要求</span><span class="sxs-lookup"><span data-stu-id="8ed0e-111">Requirements</span></span>  
 <span data-ttu-id="8ed0e-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ed0e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ed0e-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ed0e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ed0e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ed0e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ed0e-115">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ed0e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
