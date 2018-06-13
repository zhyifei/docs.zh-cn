---
title: ICorDebugNativeFrame2::GetStackParameterSize 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76ff2e502859bff27ee29a280e0d247ca1bbf1e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419551"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="f2da8-102">ICorDebugNativeFrame2::GetStackParameterSize 方法</span><span class="sxs-lookup"><span data-stu-id="f2da8-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="f2da8-103">在 x86 操作系统上的堆栈上返回参数的累积大小。</span><span class="sxs-lookup"><span data-stu-id="f2da8-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2da8-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2da8-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2da8-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2da8-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="f2da8-106">[out]指向堆栈上的参数的累积大小的指针。</span><span class="sxs-lookup"><span data-stu-id="f2da8-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2da8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f2da8-107">Return Value</span></span>  
 <span data-ttu-id="f2da8-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="f2da8-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f2da8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2da8-109">HRESULT</span></span>|<span data-ttu-id="f2da8-110">描述</span><span class="sxs-lookup"><span data-stu-id="f2da8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2da8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2da8-111">S_OK</span></span>|<span data-ttu-id="f2da8-112">成功地返回的堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="f2da8-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="f2da8-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f2da8-113">S_FALSE</span></span>|<span data-ttu-id="f2da8-114">`GetStackParameterSize` 已调用在非 x86 平台上。</span><span class="sxs-lookup"><span data-stu-id="f2da8-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="f2da8-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2da8-115">E_FAIL</span></span>|<span data-ttu-id="f2da8-116">`The size of the parameters could not be returned`。</span><span class="sxs-lookup"><span data-stu-id="f2da8-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="f2da8-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f2da8-117">E_INVALIDARG</span></span>|<span data-ttu-id="f2da8-118">`pSize` 是`null`。</span><span class="sxs-lookup"><span data-stu-id="f2da8-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f2da8-119">异常</span><span class="sxs-lookup"><span data-stu-id="f2da8-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2da8-120">备注</span><span class="sxs-lookup"><span data-stu-id="f2da8-120">Remarks</span></span>  
 <span data-ttu-id="f2da8-121">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)方法不调整参数推送到堆栈的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="f2da8-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="f2da8-122">相反，你可以使用返回的值`GetStackParameterSize`调整堆栈指针设定种子的参数未调整一个本机开卷机。</span><span class="sxs-lookup"><span data-stu-id="f2da8-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2da8-123">要求</span><span class="sxs-lookup"><span data-stu-id="f2da8-123">Requirements</span></span>  
 <span data-ttu-id="f2da8-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2da8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2da8-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2da8-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2da8-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2da8-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2da8-127">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2da8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2da8-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2da8-128">See Also</span></span>  
 [<span data-ttu-id="f2da8-129">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="f2da8-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="f2da8-130">调试接口</span><span class="sxs-lookup"><span data-stu-id="f2da8-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f2da8-131">调试</span><span class="sxs-lookup"><span data-stu-id="f2da8-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
