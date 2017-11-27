---
title: "ICorDebugNativeFrame2::GetStackParameterSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2.GetStackParameterSize Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c265cb564718b362b1354189e59dc217b2866b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="fa285-102">ICorDebugNativeFrame2::GetStackParameterSize 方法</span><span class="sxs-lookup"><span data-stu-id="fa285-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="fa285-103">在 x86 操作系统上的堆栈上返回参数的累积大小。</span><span class="sxs-lookup"><span data-stu-id="fa285-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa285-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa285-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa285-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa285-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="fa285-106">[out]指向堆栈上的参数的累积大小的指针。</span><span class="sxs-lookup"><span data-stu-id="fa285-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa285-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fa285-107">Return Value</span></span>  
 <span data-ttu-id="fa285-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="fa285-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fa285-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa285-109">HRESULT</span></span>|<span data-ttu-id="fa285-110">描述</span><span class="sxs-lookup"><span data-stu-id="fa285-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa285-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa285-111">S_OK</span></span>|<span data-ttu-id="fa285-112">成功地返回的堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="fa285-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="fa285-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fa285-113">S_FALSE</span></span>|<span data-ttu-id="fa285-114">`GetStackParameterSize`已调用在非 x86 平台上。</span><span class="sxs-lookup"><span data-stu-id="fa285-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="fa285-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa285-115">E_FAIL</span></span>|<span data-ttu-id="fa285-116">`The size of the parameters could not be returned`。</span><span class="sxs-lookup"><span data-stu-id="fa285-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="fa285-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fa285-117">E_INVALIDARG</span></span>|<span data-ttu-id="fa285-118">`pSize`是`null`。</span><span class="sxs-lookup"><span data-stu-id="fa285-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="fa285-119">异常</span><span class="sxs-lookup"><span data-stu-id="fa285-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa285-120">备注</span><span class="sxs-lookup"><span data-stu-id="fa285-120">Remarks</span></span>  
 <span data-ttu-id="fa285-121">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)方法不调整参数推送到堆栈的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="fa285-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="fa285-122">相反，你可以使用返回的值`GetStackParameterSize`调整堆栈指针设定种子的参数未调整一个本机开卷机。</span><span class="sxs-lookup"><span data-stu-id="fa285-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa285-123">要求</span><span class="sxs-lookup"><span data-stu-id="fa285-123">Requirements</span></span>  
 <span data-ttu-id="fa285-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa285-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa285-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa285-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa285-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa285-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa285-127">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa285-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa285-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa285-128">See Also</span></span>  
 [<span data-ttu-id="fa285-129">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="fa285-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="fa285-130">调试接口</span><span class="sxs-lookup"><span data-stu-id="fa285-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fa285-131">调试</span><span class="sxs-lookup"><span data-stu-id="fa285-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
