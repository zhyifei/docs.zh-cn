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
ms.openlocfilehash: f7ed7787f0302826cab67664780177f05e551199
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421101"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="f6748-102">ICorDebugThread2::GetActiveFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="f6748-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="f6748-103">每个此线程的帧中获取有关活动函数的信息。</span><span class="sxs-lookup"><span data-stu-id="f6748-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6748-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6748-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6748-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6748-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="f6748-106">[in] `pFunctions` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="f6748-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="f6748-107">[out]指向的对象中返回数的指针`pFunctions`数组。</span><span class="sxs-lookup"><span data-stu-id="f6748-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="f6748-108">返回的对象数将减至的堆栈上的托管帧的数目。</span><span class="sxs-lookup"><span data-stu-id="f6748-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="f6748-109">[在中，out]COR_ACTIVE_FUNCTION 对象数组，其中每个包含有关中此线程的帧的活动函数的信息。</span><span class="sxs-lookup"><span data-stu-id="f6748-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="f6748-110">第一个元素将用于叶帧和等回堆栈的根。</span><span class="sxs-lookup"><span data-stu-id="f6748-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6748-111">备注</span><span class="sxs-lookup"><span data-stu-id="f6748-111">Remarks</span></span>  
 <span data-ttu-id="f6748-112">如果`pFunctions`的输入，为 null`GetActiveFunctions`返回仅位于堆栈上的函数的数量。</span><span class="sxs-lookup"><span data-stu-id="f6748-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="f6748-113">也就是说，如果`pFunctions`的输入，为 null`GetActiveFunctions`返回一个值仅在`pcFunctions`。</span><span class="sxs-lookup"><span data-stu-id="f6748-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="f6748-114">`GetActiveFunctions`方法旨在作为一种优化通过从堆栈跟踪中的帧中获取相同的信息，包括，则必须 ICorDebugILFrame 对象为其在完整的堆栈跟踪中的帧。</span><span class="sxs-lookup"><span data-stu-id="f6748-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6748-115">要求</span><span class="sxs-lookup"><span data-stu-id="f6748-115">Requirements</span></span>  
 <span data-ttu-id="f6748-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6748-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6748-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6748-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6748-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6748-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6748-119">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6748-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
