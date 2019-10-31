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
ms.openlocfilehash: 9b9a301714ea60b4e3220eb75721e56e39bd9659
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139928"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="23d51-102">ICorDebugThread2::GetActiveFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="23d51-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="23d51-103">获取有关此线程的每个帧中的活动函数的信息。</span><span class="sxs-lookup"><span data-stu-id="23d51-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d51-104">语法</span><span class="sxs-lookup"><span data-stu-id="23d51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23d51-105">参数</span><span class="sxs-lookup"><span data-stu-id="23d51-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="23d51-106">[in] `pFunctions` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="23d51-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="23d51-107">弄一个指针，指向 `pFunctions` 数组中返回的对象数。</span><span class="sxs-lookup"><span data-stu-id="23d51-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="23d51-108">返回的对象数将等于堆栈上托管帧的数目。</span><span class="sxs-lookup"><span data-stu-id="23d51-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="23d51-109">[in，out]COR_ACTIVE_FUNCTION 对象的数组，其中每个对象都包含有关此线程的帧中的活动函数的信息。</span><span class="sxs-lookup"><span data-stu-id="23d51-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="23d51-110">第一个元素将用于叶帧，并回到堆栈的根目录。</span><span class="sxs-lookup"><span data-stu-id="23d51-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23d51-111">备注</span><span class="sxs-lookup"><span data-stu-id="23d51-111">Remarks</span></span>  
 <span data-ttu-id="23d51-112">如果 `pFunctions` 在输入时为 null，`GetActiveFunctions` 只返回堆栈上的函数数。</span><span class="sxs-lookup"><span data-stu-id="23d51-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="23d51-113">也就是说，如果在输入 `pFunctions` 为 null，则 `GetActiveFunctions` 仅在 `pcFunctions`中返回值。</span><span class="sxs-lookup"><span data-stu-id="23d51-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="23d51-114">`GetActiveFunctions` 方法旨在优化堆栈跟踪中的帧获取相同的信息，并且仅包含在完整堆栈跟踪中具有 ICorDebugILFrame 对象的帧。</span><span class="sxs-lookup"><span data-stu-id="23d51-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23d51-115">要求</span><span class="sxs-lookup"><span data-stu-id="23d51-115">Requirements</span></span>  
 <span data-ttu-id="23d51-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23d51-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d51-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23d51-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23d51-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23d51-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23d51-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23d51-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
