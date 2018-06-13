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
ms.openlocfilehash: 226f8c431b90d53366aa5e504101e7de581ec570
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402465"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="69b7b-102">ICorDebugChain::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="69b7b-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="69b7b-103">获取此证书链的堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="69b7b-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69b7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="69b7b-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69b7b-105">参数</span><span class="sxs-lookup"><span data-stu-id="69b7b-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="69b7b-106">[out]指向的指针`CORDB_ADDRESS`是堆栈段的起始地址的值。</span><span class="sxs-lookup"><span data-stu-id="69b7b-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="69b7b-107">[out]指向的指针`CORDB_ADDRESS`是堆栈段的结束地址的值。</span><span class="sxs-lookup"><span data-stu-id="69b7b-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69b7b-108">备注</span><span class="sxs-lookup"><span data-stu-id="69b7b-108">Remarks</span></span>  
 <span data-ttu-id="69b7b-109">数值范围是仅对比较的堆栈帧位置有意义。</span><span class="sxs-lookup"><span data-stu-id="69b7b-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="69b7b-110">不能进行任何假设在堆栈上实际存储的内容。</span><span class="sxs-lookup"><span data-stu-id="69b7b-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69b7b-111">要求</span><span class="sxs-lookup"><span data-stu-id="69b7b-111">Requirements</span></span>  
 <span data-ttu-id="69b7b-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="69b7b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69b7b-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69b7b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69b7b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69b7b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69b7b-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69b7b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
