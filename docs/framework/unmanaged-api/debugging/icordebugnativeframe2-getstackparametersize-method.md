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
ms.openlocfilehash: b88b3907eb555050de93f35411629b2bd30c7375
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212940"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="b5e97-102">ICorDebugNativeFrame2::GetStackParameterSize 方法</span><span class="sxs-lookup"><span data-stu-id="b5e97-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="b5e97-103">返回 x86 操作系统上堆栈上的参数的累积大小。</span><span class="sxs-lookup"><span data-stu-id="b5e97-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e97-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5e97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5e97-105">参数</span><span class="sxs-lookup"><span data-stu-id="b5e97-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="b5e97-106">弄指向堆栈上参数的累计大小的指针。</span><span class="sxs-lookup"><span data-stu-id="b5e97-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5e97-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b5e97-107">Return Value</span></span>  
 <span data-ttu-id="b5e97-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="b5e97-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b5e97-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5e97-109">HRESULT</span></span>|<span data-ttu-id="b5e97-110">描述</span><span class="sxs-lookup"><span data-stu-id="b5e97-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5e97-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5e97-111">S_OK</span></span>|<span data-ttu-id="b5e97-112">堆栈大小已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b5e97-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="b5e97-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b5e97-113">S_FALSE</span></span>|<span data-ttu-id="b5e97-114">`GetStackParameterSize`在非 x86 平台上调用了。</span><span class="sxs-lookup"><span data-stu-id="b5e97-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="b5e97-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b5e97-115">E_FAIL</span></span>|<span data-ttu-id="b5e97-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="b5e97-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="b5e97-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b5e97-117">E_INVALIDARG</span></span>|<span data-ttu-id="b5e97-118">`pSize`为 `null` 。</span><span class="sxs-lookup"><span data-stu-id="b5e97-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b5e97-119">例外</span><span class="sxs-lookup"><span data-stu-id="b5e97-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5e97-120">备注</span><span class="sxs-lookup"><span data-stu-id="b5e97-120">Remarks</span></span>  
 <span data-ttu-id="b5e97-121">[ICorDebugStackWalk](icordebugstackwalk-interface.md)方法不调整推送到堆栈上的参数的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="b5e97-121">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="b5e97-122">相反，你可以使用返回的值 `GetStackParameterSize` 调整堆栈指针，使其成为本机展开器的种子，这会调整参数。</span><span class="sxs-lookup"><span data-stu-id="b5e97-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5e97-123">要求</span><span class="sxs-lookup"><span data-stu-id="b5e97-123">Requirements</span></span>  
 <span data-ttu-id="b5e97-124">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5e97-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5e97-125">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5e97-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5e97-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5e97-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5e97-127">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e97-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e97-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5e97-128">See also</span></span>

- [<span data-ttu-id="b5e97-129">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="b5e97-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="b5e97-130">调试接口</span><span class="sxs-lookup"><span data-stu-id="b5e97-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b5e97-131">调试</span><span class="sxs-lookup"><span data-stu-id="b5e97-131">Debugging</span></span>](index.md)
