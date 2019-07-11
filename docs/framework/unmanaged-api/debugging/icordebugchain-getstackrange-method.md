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
ms.openlocfilehash: 8a6db1990df2ed6b29d548c147ed40b5bc98254d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745693"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="ff980-102">ICorDebugChain::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="ff980-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="ff980-103">获取此链堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="ff980-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff980-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff980-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff980-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff980-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="ff980-106">[out]一个指向`CORDB_ADDRESS`堆栈段的起始地址的值。</span><span class="sxs-lookup"><span data-stu-id="ff980-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="ff980-107">[out]一个指向`CORDB_ADDRESS`是堆栈段的结束地址的值。</span><span class="sxs-lookup"><span data-stu-id="ff980-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff980-108">备注</span><span class="sxs-lookup"><span data-stu-id="ff980-108">Remarks</span></span>  
 <span data-ttu-id="ff980-109">数值范围是仅对的堆栈帧位置比较有意义。</span><span class="sxs-lookup"><span data-stu-id="ff980-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="ff980-110">不能进行任何假设实际存储在堆栈上的内容。</span><span class="sxs-lookup"><span data-stu-id="ff980-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff980-111">要求</span><span class="sxs-lookup"><span data-stu-id="ff980-111">Requirements</span></span>  
 <span data-ttu-id="ff980-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff980-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff980-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff980-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff980-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff980-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff980-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff980-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
