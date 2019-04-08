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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9503c12da9e98fbd43f3904aad25c5d10655cec2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075556"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="d3392-102">ICorDebugNativeFrame2::IsChild 方法</span><span class="sxs-lookup"><span data-stu-id="d3392-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="d3392-103">确定当前帧是否为子框架。</span><span class="sxs-lookup"><span data-stu-id="d3392-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3392-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3392-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3392-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3392-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="d3392-106">[out]一个布尔值，该值指定当前帧是否为子框架。</span><span class="sxs-lookup"><span data-stu-id="d3392-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3392-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d3392-107">Return Value</span></span>  
 <span data-ttu-id="d3392-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="d3392-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d3392-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3392-109">HRESULT</span></span>|<span data-ttu-id="d3392-110">描述</span><span class="sxs-lookup"><span data-stu-id="d3392-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3392-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3392-111">S_OK</span></span>|<span data-ttu-id="d3392-112">成功地返回子状态。</span><span class="sxs-lookup"><span data-stu-id="d3392-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="d3392-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3392-113">E_FAIL</span></span>|<span data-ttu-id="d3392-114">不会返回子状态。</span><span class="sxs-lookup"><span data-stu-id="d3392-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="d3392-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d3392-115">E_INVALIDARG</span></span>|`pIsChild` <span data-ttu-id="d3392-116">为 null。</span><span class="sxs-lookup"><span data-stu-id="d3392-116">is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d3392-117">Exceptions</span><span class="sxs-lookup"><span data-stu-id="d3392-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3392-118">备注</span><span class="sxs-lookup"><span data-stu-id="d3392-118">Remarks</span></span>  
 <span data-ttu-id="d3392-119">`IsChild`方法将返回`true`框架对象调用该方法是否是另一个帧的子级。</span><span class="sxs-lookup"><span data-stu-id="d3392-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="d3392-120">如果这种情况，请使用[IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)方法来检查帧是否作为其父级。</span><span class="sxs-lookup"><span data-stu-id="d3392-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3392-121">要求</span><span class="sxs-lookup"><span data-stu-id="d3392-121">Requirements</span></span>  
 <span data-ttu-id="d3392-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3392-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3392-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3392-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3392-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3392-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d3392-125">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d3392-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3392-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3392-126">See also</span></span>

- [<span data-ttu-id="d3392-127">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="d3392-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="d3392-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="d3392-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d3392-129">调试</span><span class="sxs-lookup"><span data-stu-id="d3392-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
