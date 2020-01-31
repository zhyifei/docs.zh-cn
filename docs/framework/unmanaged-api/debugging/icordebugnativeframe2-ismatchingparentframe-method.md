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
ms.openlocfilehash: aeaa706ef35413a728f8b254cd325f0bcc83acd1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792717"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="4a705-102">ICorDebugNativeFrame2::IsMatchingParentFrame 方法</span><span class="sxs-lookup"><span data-stu-id="4a705-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="4a705-103">确定指定的帧是否为当前帧的父级。</span><span class="sxs-lookup"><span data-stu-id="4a705-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a705-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a705-104">Syntax</span></span>  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a705-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a705-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="4a705-106">中一个指针，指向要为父状态计算的帧对象。</span><span class="sxs-lookup"><span data-stu-id="4a705-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="4a705-107">[out] 如果 `pPotentialParentFrame` 为当前帧的父级，则为 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="4a705-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a705-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4a705-108">Return Value</span></span>  
 <span data-ttu-id="4a705-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="4a705-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4a705-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a705-110">HRESULT</span></span>|<span data-ttu-id="4a705-111">描述</span><span class="sxs-lookup"><span data-stu-id="4a705-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a705-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a705-112">S_OK</span></span>|<span data-ttu-id="4a705-113">父状态已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4a705-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="4a705-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a705-114">E_FAIL</span></span>|<span data-ttu-id="4a705-115">无法返回父状态。</span><span class="sxs-lookup"><span data-stu-id="4a705-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="4a705-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4a705-116">E_INVALIDARG</span></span>|<span data-ttu-id="4a705-117">`pPotentialParentFrame` 或 `pIsParent` 为 null。</span><span class="sxs-lookup"><span data-stu-id="4a705-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4a705-118">异常</span><span class="sxs-lookup"><span data-stu-id="4a705-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a705-119">备注</span><span class="sxs-lookup"><span data-stu-id="4a705-119">Remarks</span></span>  
 <span data-ttu-id="4a705-120">如果传递给该方法的帧对象是在其上调用方法的 frame 对象的父对象，`IsMatchingParentFrame` 将返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="4a705-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="4a705-121">如果在不是指定帧的子级的帧上调用方法，则会返回错误。</span><span class="sxs-lookup"><span data-stu-id="4a705-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a705-122">需求</span><span class="sxs-lookup"><span data-stu-id="4a705-122">Requirements</span></span>  
 <span data-ttu-id="4a705-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a705-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a705-124">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a705-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a705-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a705-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a705-126">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a705-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a705-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a705-127">See also</span></span>

- [<span data-ttu-id="4a705-128">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="4a705-128">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="4a705-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="4a705-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4a705-130">调试</span><span class="sxs-lookup"><span data-stu-id="4a705-130">Debugging</span></span>](index.md)
