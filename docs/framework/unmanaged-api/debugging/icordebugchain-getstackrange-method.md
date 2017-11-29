---
title: "ICorDebugChain::GetStackRange 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetStackRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce5e42bb9374f22ad29ef0e97a141a796f087a98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="1f529-102">ICorDebugChain::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="1f529-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="1f529-103">获取此证书链的堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="1f529-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f529-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f529-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f529-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f529-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="1f529-106">[out]指向的指针`CORDB_ADDRESS`是堆栈段的起始地址的值。</span><span class="sxs-lookup"><span data-stu-id="1f529-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="1f529-107">[out]指向的指针`CORDB_ADDRESS`是堆栈段的结束地址的值。</span><span class="sxs-lookup"><span data-stu-id="1f529-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f529-108">备注</span><span class="sxs-lookup"><span data-stu-id="1f529-108">Remarks</span></span>  
 <span data-ttu-id="1f529-109">数值范围是仅对比较的堆栈帧位置有意义。</span><span class="sxs-lookup"><span data-stu-id="1f529-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="1f529-110">不能进行任何假设在堆栈上实际存储的内容。</span><span class="sxs-lookup"><span data-stu-id="1f529-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f529-111">要求</span><span class="sxs-lookup"><span data-stu-id="1f529-111">Requirements</span></span>  
 <span data-ttu-id="1f529-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f529-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f529-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f529-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f529-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f529-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f529-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f529-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
