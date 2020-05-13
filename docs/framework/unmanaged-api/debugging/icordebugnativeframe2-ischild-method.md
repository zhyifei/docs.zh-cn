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
ms.openlocfilehash: 759ba7bd46f8231143e743aa5ffcabffeb99c3b6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205102"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="c6013-102">ICorDebugNativeFrame2::IsChild 方法</span><span class="sxs-lookup"><span data-stu-id="c6013-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="c6013-103">确定当前帧是否为子框架。</span><span class="sxs-lookup"><span data-stu-id="c6013-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6013-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6013-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6013-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6013-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="c6013-106">弄指定当前帧是否为子框架的布尔值。</span><span class="sxs-lookup"><span data-stu-id="c6013-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6013-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c6013-107">Return Value</span></span>  
 <span data-ttu-id="c6013-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="c6013-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c6013-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6013-109">HRESULT</span></span>|<span data-ttu-id="c6013-110">描述</span><span class="sxs-lookup"><span data-stu-id="c6013-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6013-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6013-111">S_OK</span></span>|<span data-ttu-id="c6013-112">已成功返回子状态。</span><span class="sxs-lookup"><span data-stu-id="c6013-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="c6013-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6013-113">E_FAIL</span></span>|<span data-ttu-id="c6013-114">无法返回子状态。</span><span class="sxs-lookup"><span data-stu-id="c6013-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="c6013-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c6013-115">E_INVALIDARG</span></span>|<span data-ttu-id="c6013-116">`pIsChild` 为 null。</span><span class="sxs-lookup"><span data-stu-id="c6013-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c6013-117">例外</span><span class="sxs-lookup"><span data-stu-id="c6013-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6013-118">备注</span><span class="sxs-lookup"><span data-stu-id="c6013-118">Remarks</span></span>  
 <span data-ttu-id="c6013-119">`IsChild` `true` 如果调用方法的帧对象是另一帧的子对象，则该方法返回。</span><span class="sxs-lookup"><span data-stu-id="c6013-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="c6013-120">如果是这种情况，请使用[IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md)方法检查帧是否为其父级。</span><span class="sxs-lookup"><span data-stu-id="c6013-120">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6013-121">要求</span><span class="sxs-lookup"><span data-stu-id="c6013-121">Requirements</span></span>  
 <span data-ttu-id="c6013-122">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6013-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6013-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6013-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6013-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6013-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6013-125">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6013-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6013-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6013-126">See also</span></span>

- [<span data-ttu-id="c6013-127">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="c6013-127">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="c6013-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="c6013-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c6013-129">调试</span><span class="sxs-lookup"><span data-stu-id="c6013-129">Debugging</span></span>](index.md)
