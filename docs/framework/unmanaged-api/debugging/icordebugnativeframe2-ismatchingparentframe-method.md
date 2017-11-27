---
title: "ICorDebugNativeFrame2::IsMatchingParentFrame 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e261f4cb43843ec61ec6cbd1609e6967a4a38a82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="b2085-102">ICorDebugNativeFrame2::IsMatchingParentFrame 方法</span><span class="sxs-lookup"><span data-stu-id="b2085-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="b2085-103">确定是否为指定的框架为当前帧的父级。</span><span class="sxs-lookup"><span data-stu-id="b2085-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2085-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2085-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2085-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2085-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="b2085-106">[in]指向想要评估父状态框架对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b2085-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="b2085-107">[out]`true`如果`pPotentialParentFrame`是当前帧的父级; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="b2085-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2085-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b2085-108">Return Value</span></span>  
 <span data-ttu-id="b2085-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="b2085-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b2085-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2085-110">HRESULT</span></span>|<span data-ttu-id="b2085-111">描述</span><span class="sxs-lookup"><span data-stu-id="b2085-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2085-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2085-112">S_OK</span></span>|<span data-ttu-id="b2085-113">成功地返回父状态。</span><span class="sxs-lookup"><span data-stu-id="b2085-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="b2085-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2085-114">E_FAIL</span></span>|<span data-ttu-id="b2085-115">不会返回父状态。</span><span class="sxs-lookup"><span data-stu-id="b2085-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="b2085-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b2085-116">E_INVALIDARG</span></span>|<span data-ttu-id="b2085-117">`pPotentialParentFrame` 或 `pIsParent` 为 null。</span><span class="sxs-lookup"><span data-stu-id="b2085-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b2085-118">异常</span><span class="sxs-lookup"><span data-stu-id="b2085-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2085-119">备注</span><span class="sxs-lookup"><span data-stu-id="b2085-119">Remarks</span></span>  
 <span data-ttu-id="b2085-120">`IsMatchingParentFrame`返回`true`框架对象传递给该方法是否在其调用方法帧对象的父级。</span><span class="sxs-lookup"><span data-stu-id="b2085-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="b2085-121">如果你在不是为指定框架的子级的帧上调用方法时，它将返回错误。</span><span class="sxs-lookup"><span data-stu-id="b2085-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2085-122">要求</span><span class="sxs-lookup"><span data-stu-id="b2085-122">Requirements</span></span>  
 <span data-ttu-id="b2085-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2085-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2085-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2085-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2085-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2085-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2085-126">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2085-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2085-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2085-127">See Also</span></span>  
 [<span data-ttu-id="b2085-128">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="b2085-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="b2085-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="b2085-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b2085-130">调试</span><span class="sxs-lookup"><span data-stu-id="b2085-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
