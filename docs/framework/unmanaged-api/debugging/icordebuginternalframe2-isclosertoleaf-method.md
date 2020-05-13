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
ms.openlocfilehash: 4a01ccd4e5cb9aadc6a693b2c6ceaff31c114bbc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209885"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="2493e-102">ICorDebugInternalFrame2::IsCloserToLeaf 方法</span><span class="sxs-lookup"><span data-stu-id="2493e-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="2493e-103">检查 `this` 内部帧是否接近于指定的 ICorDebugFrame 对象。</span><span class="sxs-lookup"><span data-stu-id="2493e-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2493e-104">语法</span><span class="sxs-lookup"><span data-stu-id="2493e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2493e-105">参数</span><span class="sxs-lookup"><span data-stu-id="2493e-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="2493e-106">中指向比较对象的指针 `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="2493e-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="2493e-107">[out] `true`如果 `this` 内部帧比指定的帧更接近叶 `pFrameToCompare` ，则为; 否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="2493e-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2493e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2493e-108">Return Value</span></span>  
 <span data-ttu-id="2493e-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="2493e-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2493e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2493e-110">HRESULT</span></span>|<span data-ttu-id="2493e-111">描述</span><span class="sxs-lookup"><span data-stu-id="2493e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2493e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2493e-112">S_OK</span></span>|<span data-ttu-id="2493e-113">已成功执行比较。</span><span class="sxs-lookup"><span data-stu-id="2493e-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="2493e-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2493e-114">E_FAIL</span></span>|<span data-ttu-id="2493e-115">无法执行比较。</span><span class="sxs-lookup"><span data-stu-id="2493e-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="2493e-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2493e-116">E_INVALIDARG</span></span>|<span data-ttu-id="2493e-117">`pFrameToCompare` 或 `pIsCloser` 为 null。</span><span class="sxs-lookup"><span data-stu-id="2493e-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2493e-118">备注</span><span class="sxs-lookup"><span data-stu-id="2493e-118">Remarks</span></span>  
 <span data-ttu-id="2493e-119">`IsCloserToLeaf`可用于实现将内部帧与堆栈上的其他帧交错的策略。</span><span class="sxs-lookup"><span data-stu-id="2493e-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2493e-120">要求</span><span class="sxs-lookup"><span data-stu-id="2493e-120">Requirements</span></span>  
 <span data-ttu-id="2493e-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2493e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2493e-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2493e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2493e-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2493e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2493e-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2493e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2493e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="2493e-125">See also</span></span>

- [<span data-ttu-id="2493e-126">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="2493e-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="2493e-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="2493e-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2493e-128">调试</span><span class="sxs-lookup"><span data-stu-id="2493e-128">Debugging</span></span>](index.md)
