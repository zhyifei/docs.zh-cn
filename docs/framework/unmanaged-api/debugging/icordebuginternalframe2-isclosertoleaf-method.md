---
title: ICorDebugInternalFrame2::IsCloserToLeaf 方法
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d26d4dc046841a891c8a36530bd579d100b8f5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416119"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="a80b6-102">ICorDebugInternalFrame2::IsCloserToLeaf 方法</span><span class="sxs-lookup"><span data-stu-id="a80b6-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="a80b6-103">检查是否`this`内部框架为更接近于叶比指定的 ICorDebugFrame 对象。</span><span class="sxs-lookup"><span data-stu-id="a80b6-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a80b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="a80b6-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a80b6-105">参数</span><span class="sxs-lookup"><span data-stu-id="a80b6-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="a80b6-106">[in]指向比较`ICorDebugFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="a80b6-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="a80b6-107">[out]`true`如果`this`内部框架为更接近于叶比指定的帧`pFrameToCompare`; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="a80b6-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a80b6-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a80b6-108">Return Value</span></span>  
 <span data-ttu-id="a80b6-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="a80b6-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a80b6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a80b6-110">HRESULT</span></span>|<span data-ttu-id="a80b6-111">描述</span><span class="sxs-lookup"><span data-stu-id="a80b6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a80b6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a80b6-112">S_OK</span></span>|<span data-ttu-id="a80b6-113">比较已成功执行。</span><span class="sxs-lookup"><span data-stu-id="a80b6-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="a80b6-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a80b6-114">E_FAIL</span></span>|<span data-ttu-id="a80b6-115">无法执行比较。</span><span class="sxs-lookup"><span data-stu-id="a80b6-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="a80b6-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a80b6-116">E_INVALIDARG</span></span>|<span data-ttu-id="a80b6-117">`pFrameToCompare` 或 `pIsCloser` 为 null。</span><span class="sxs-lookup"><span data-stu-id="a80b6-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a80b6-118">备注</span><span class="sxs-lookup"><span data-stu-id="a80b6-118">Remarks</span></span>  
 <span data-ttu-id="a80b6-119">`IsCloserToLeaf` 可以用于实现进行交替使用堆栈上的其他框架的内部帧的策略。</span><span class="sxs-lookup"><span data-stu-id="a80b6-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a80b6-120">要求</span><span class="sxs-lookup"><span data-stu-id="a80b6-120">Requirements</span></span>  
 <span data-ttu-id="a80b6-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a80b6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a80b6-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a80b6-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a80b6-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a80b6-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a80b6-124">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a80b6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a80b6-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a80b6-125">See Also</span></span>  
 [<span data-ttu-id="a80b6-126">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="a80b6-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="a80b6-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="a80b6-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a80b6-128">调试</span><span class="sxs-lookup"><span data-stu-id="a80b6-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
