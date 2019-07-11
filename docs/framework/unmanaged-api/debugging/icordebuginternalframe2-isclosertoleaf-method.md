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
ms.openlocfilehash: c0e72d15ab4ca9b4468efb2a671022f30bfb3cc6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759943"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="592c7-102">ICorDebugInternalFrame2::IsCloserToLeaf 方法</span><span class="sxs-lookup"><span data-stu-id="592c7-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="592c7-103">检查是否`this`内部框架是比指定 ICorDebugFrame 对象更接近于叶。</span><span class="sxs-lookup"><span data-stu-id="592c7-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="592c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="592c7-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="592c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="592c7-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="592c7-106">[in]指向比较`ICorDebugFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="592c7-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="592c7-107">[out]`true`如果`this`内部框架是比指定的帧更接近于叶`pFrameToCompare`; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="592c7-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="592c7-108">返回值</span><span class="sxs-lookup"><span data-stu-id="592c7-108">Return Value</span></span>  
 <span data-ttu-id="592c7-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="592c7-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="592c7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="592c7-110">HRESULT</span></span>|<span data-ttu-id="592c7-111">描述</span><span class="sxs-lookup"><span data-stu-id="592c7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="592c7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="592c7-112">S_OK</span></span>|<span data-ttu-id="592c7-113">已成功执行比较。</span><span class="sxs-lookup"><span data-stu-id="592c7-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="592c7-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="592c7-114">E_FAIL</span></span>|<span data-ttu-id="592c7-115">无法执行比较。</span><span class="sxs-lookup"><span data-stu-id="592c7-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="592c7-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="592c7-116">E_INVALIDARG</span></span>|<span data-ttu-id="592c7-117">`pFrameToCompare` 或 `pIsCloser` 为 null。</span><span class="sxs-lookup"><span data-stu-id="592c7-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="592c7-118">备注</span><span class="sxs-lookup"><span data-stu-id="592c7-118">Remarks</span></span>  
 <span data-ttu-id="592c7-119">`IsCloserToLeaf` 可以用于实现适用于内部帧与堆栈上的其他框架在交错执行的策略。</span><span class="sxs-lookup"><span data-stu-id="592c7-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="592c7-120">要求</span><span class="sxs-lookup"><span data-stu-id="592c7-120">Requirements</span></span>  
 <span data-ttu-id="592c7-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="592c7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="592c7-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="592c7-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="592c7-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="592c7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="592c7-124">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="592c7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="592c7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="592c7-125">See also</span></span>

- [<span data-ttu-id="592c7-126">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="592c7-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="592c7-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="592c7-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="592c7-128">调试</span><span class="sxs-lookup"><span data-stu-id="592c7-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
