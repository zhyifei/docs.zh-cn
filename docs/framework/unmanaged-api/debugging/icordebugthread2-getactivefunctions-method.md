---
title: ICorDebugThread2::GetActiveFunctions 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed13f78d5a1f6d54b12c86613715f4878a521bfa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489925"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="e54b2-102">ICorDebugThread2::GetActiveFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="e54b2-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="e54b2-103">在每个此线程的帧中获取有关活动函数的信息。</span><span class="sxs-lookup"><span data-stu-id="e54b2-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e54b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="e54b2-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e54b2-105">参数</span><span class="sxs-lookup"><span data-stu-id="e54b2-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="e54b2-106">[in] `pFunctions` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="e54b2-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="e54b2-107">[out]指向中返回的对象数的`pFunctions`数组。</span><span class="sxs-lookup"><span data-stu-id="e54b2-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="e54b2-108">返回的对象数目将等于在堆栈上的托管帧数。</span><span class="sxs-lookup"><span data-stu-id="e54b2-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="e54b2-109">[in、 out]COR_ACTIVE_FUNCTION 对象数组，其中每个包含有关此线程的帧中的活动函数的信息。</span><span class="sxs-lookup"><span data-stu-id="e54b2-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="e54b2-110">第一个元素将用于叶帧，因此，在返回到堆栈的根。</span><span class="sxs-lookup"><span data-stu-id="e54b2-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e54b2-111">备注</span><span class="sxs-lookup"><span data-stu-id="e54b2-111">Remarks</span></span>  
 <span data-ttu-id="e54b2-112">如果`pFunctions`的输入，为 null`GetActiveFunctions`只返回数的函数的堆栈上。</span><span class="sxs-lookup"><span data-stu-id="e54b2-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="e54b2-113">也就是说，如果`pFunctions`的输入，为 null`GetActiveFunctions`返回的值仅在`pcFunctions`。</span><span class="sxs-lookup"><span data-stu-id="e54b2-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="e54b2-114">`GetActiveFunctions`方法旨在作为一种优化，通过从堆栈跟踪中的帧中获取相同信息并包括，则必须 ICorDebugILFrame 对象为其完整的堆栈跟踪中的帧。</span><span class="sxs-lookup"><span data-stu-id="e54b2-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e54b2-115">要求</span><span class="sxs-lookup"><span data-stu-id="e54b2-115">Requirements</span></span>  
 <span data-ttu-id="e54b2-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e54b2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e54b2-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e54b2-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e54b2-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e54b2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e54b2-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e54b2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
