---
title: ICorDebugNativeFrame2::IsMatchingParentFrame 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39c0ea69a0922f5e0d25c98c21ec17a872b2f421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418865"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="a1c18-102">ICorDebugNativeFrame2::IsMatchingParentFrame 方法</span><span class="sxs-lookup"><span data-stu-id="a1c18-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="a1c18-103">确定是否为指定的框架为当前帧的父级。</span><span class="sxs-lookup"><span data-stu-id="a1c18-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c18-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1c18-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1c18-105">参数</span><span class="sxs-lookup"><span data-stu-id="a1c18-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="a1c18-106">[in]指向想要评估父状态框架对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a1c18-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="a1c18-107">[out]`true`如果`pPotentialParentFrame`是当前帧的父级; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="a1c18-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1c18-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a1c18-108">Return Value</span></span>  
 <span data-ttu-id="a1c18-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="a1c18-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a1c18-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1c18-110">HRESULT</span></span>|<span data-ttu-id="a1c18-111">描述</span><span class="sxs-lookup"><span data-stu-id="a1c18-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1c18-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1c18-112">S_OK</span></span>|<span data-ttu-id="a1c18-113">成功地返回父状态。</span><span class="sxs-lookup"><span data-stu-id="a1c18-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="a1c18-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1c18-114">E_FAIL</span></span>|<span data-ttu-id="a1c18-115">不会返回父状态。</span><span class="sxs-lookup"><span data-stu-id="a1c18-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="a1c18-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a1c18-116">E_INVALIDARG</span></span>|<span data-ttu-id="a1c18-117">`pPotentialParentFrame` 或 `pIsParent` 为 null。</span><span class="sxs-lookup"><span data-stu-id="a1c18-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a1c18-118">异常</span><span class="sxs-lookup"><span data-stu-id="a1c18-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1c18-119">备注</span><span class="sxs-lookup"><span data-stu-id="a1c18-119">Remarks</span></span>  
 <span data-ttu-id="a1c18-120">`IsMatchingParentFrame` 返回`true`框架对象传递给该方法是否在其调用方法帧对象的父级。</span><span class="sxs-lookup"><span data-stu-id="a1c18-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="a1c18-121">如果你在不是为指定框架的子级的帧上调用方法时，它将返回错误。</span><span class="sxs-lookup"><span data-stu-id="a1c18-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1c18-122">要求</span><span class="sxs-lookup"><span data-stu-id="a1c18-122">Requirements</span></span>  
 <span data-ttu-id="a1c18-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c18-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1c18-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1c18-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1c18-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1c18-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1c18-126">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1c18-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c18-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1c18-127">See Also</span></span>  
 [<span data-ttu-id="a1c18-128">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="a1c18-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="a1c18-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="a1c18-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a1c18-130">调试</span><span class="sxs-lookup"><span data-stu-id="a1c18-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
