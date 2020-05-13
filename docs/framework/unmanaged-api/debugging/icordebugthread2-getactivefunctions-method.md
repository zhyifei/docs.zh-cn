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
ms.openlocfilehash: e064a7db131a671adc4d0b6df522f3456e3a31d5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377157"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="0cd34-102">ICorDebugThread2::GetActiveFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="0cd34-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="0cd34-103">获取有关此线程的每个帧中的活动函数的信息。</span><span class="sxs-lookup"><span data-stu-id="0cd34-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cd34-104">语法</span><span class="sxs-lookup"><span data-stu-id="0cd34-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cd34-105">参数</span><span class="sxs-lookup"><span data-stu-id="0cd34-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="0cd34-106">[in] `pFunctions` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="0cd34-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="0cd34-107">弄一个指针，它指向数组中返回的对象的数目 `pFunctions` 。</span><span class="sxs-lookup"><span data-stu-id="0cd34-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="0cd34-108">返回的对象数将等于堆栈上托管帧的数目。</span><span class="sxs-lookup"><span data-stu-id="0cd34-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="0cd34-109">[in，out]COR_ACTIVE_FUNCTION 对象的数组，其中每个对象都包含有关此线程的帧中的活动函数的信息。</span><span class="sxs-lookup"><span data-stu-id="0cd34-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="0cd34-110">第一个元素将用于叶帧，并回到堆栈的根目录。</span><span class="sxs-lookup"><span data-stu-id="0cd34-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cd34-111">备注</span><span class="sxs-lookup"><span data-stu-id="0cd34-111">Remarks</span></span>  
 <span data-ttu-id="0cd34-112">如果 `pFunctions` 在输入时为 null，则 `GetActiveFunctions` 仅返回堆栈上的函数数目。</span><span class="sxs-lookup"><span data-stu-id="0cd34-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="0cd34-113">也就是说，如果在 `pFunctions` 输入时为 null，则 `GetActiveFunctions` 仅返回中的值 `pcFunctions` 。</span><span class="sxs-lookup"><span data-stu-id="0cd34-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="0cd34-114">`GetActiveFunctions`方法旨在优化堆栈跟踪中的帧获取相同的信息，并且仅包含在完整堆栈跟踪中具有 ICorDebugILFrame 对象的帧。</span><span class="sxs-lookup"><span data-stu-id="0cd34-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cd34-115">要求</span><span class="sxs-lookup"><span data-stu-id="0cd34-115">Requirements</span></span>  
 <span data-ttu-id="0cd34-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0cd34-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cd34-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cd34-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cd34-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cd34-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cd34-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cd34-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
