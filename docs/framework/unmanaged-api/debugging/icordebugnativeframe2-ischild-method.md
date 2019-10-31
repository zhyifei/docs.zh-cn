---
title: ICorDebugNativeFrame2::IsChild 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
ms.openlocfilehash: 539fa612234c4cc37bed5a8fd4b1e727a35b1d6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096389"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="ae845-102">ICorDebugNativeFrame2::IsChild 方法</span><span class="sxs-lookup"><span data-stu-id="ae845-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="ae845-103">确定当前帧是否为子框架。</span><span class="sxs-lookup"><span data-stu-id="ae845-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae845-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae845-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae845-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae845-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="ae845-106">弄指定当前帧是否为子框架的布尔值。</span><span class="sxs-lookup"><span data-stu-id="ae845-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae845-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ae845-107">Return Value</span></span>  
 <span data-ttu-id="ae845-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ae845-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ae845-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae845-109">HRESULT</span></span>|<span data-ttu-id="ae845-110">描述</span><span class="sxs-lookup"><span data-stu-id="ae845-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae845-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae845-111">S_OK</span></span>|<span data-ttu-id="ae845-112">已成功返回子状态。</span><span class="sxs-lookup"><span data-stu-id="ae845-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="ae845-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae845-113">E_FAIL</span></span>|<span data-ttu-id="ae845-114">无法返回子状态。</span><span class="sxs-lookup"><span data-stu-id="ae845-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="ae845-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ae845-115">E_INVALIDARG</span></span>|<span data-ttu-id="ae845-116">`pIsChild` 为 null。</span><span class="sxs-lookup"><span data-stu-id="ae845-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ae845-117">异常</span><span class="sxs-lookup"><span data-stu-id="ae845-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae845-118">备注</span><span class="sxs-lookup"><span data-stu-id="ae845-118">Remarks</span></span>  
 <span data-ttu-id="ae845-119">如果调用方法的帧对象是另一帧的子对象，则 `IsChild` 方法返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="ae845-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="ae845-120">如果是这种情况，请使用[IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)方法检查帧是否为其父级。</span><span class="sxs-lookup"><span data-stu-id="ae845-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae845-121">要求</span><span class="sxs-lookup"><span data-stu-id="ae845-121">Requirements</span></span>  
 <span data-ttu-id="ae845-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae845-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae845-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae845-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae845-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae845-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae845-125">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae845-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae845-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae845-126">See also</span></span>

- [<span data-ttu-id="ae845-127">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="ae845-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="ae845-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="ae845-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ae845-129">调试</span><span class="sxs-lookup"><span data-stu-id="ae845-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
