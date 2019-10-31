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
ms.openlocfilehash: d9430c5a1f37a0507b383ea5437f7d7fed706c43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123867"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="c86ea-102">ICorDebugChain::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="c86ea-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="c86ea-103">获取此链的堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="c86ea-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c86ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="c86ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c86ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="c86ea-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="c86ea-106">弄一个指针，指向作为堆栈段起始地址的 `CORDB_ADDRESS` 值。</span><span class="sxs-lookup"><span data-stu-id="c86ea-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="c86ea-107">弄一个指针，指向作为堆栈段结束地址的 `CORDB_ADDRESS` 值。</span><span class="sxs-lookup"><span data-stu-id="c86ea-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c86ea-108">备注</span><span class="sxs-lookup"><span data-stu-id="c86ea-108">Remarks</span></span>  
 <span data-ttu-id="c86ea-109">数值范围仅用于比较堆栈帧位置。</span><span class="sxs-lookup"><span data-stu-id="c86ea-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="c86ea-110">您无法对堆栈上实际存储的内容作出任何假设。</span><span class="sxs-lookup"><span data-stu-id="c86ea-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c86ea-111">要求</span><span class="sxs-lookup"><span data-stu-id="c86ea-111">Requirements</span></span>  
 <span data-ttu-id="c86ea-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c86ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c86ea-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c86ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c86ea-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c86ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c86ea-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c86ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
