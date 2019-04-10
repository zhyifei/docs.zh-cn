---
title: ICorDebugInternalFrame2::GetFrameAddress 方法
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c30115a23f7f73662c9b3f4f4a09d45478ad687
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187286"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="146ab-102">ICorDebugInternalFrame2::GetFrameAddress 方法</span><span class="sxs-lookup"><span data-stu-id="146ab-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="146ab-103">返回内部帧的堆栈地址。</span><span class="sxs-lookup"><span data-stu-id="146ab-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="146ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="146ab-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="146ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="146ab-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="146ab-106">[out]指向`CORDB_ADDRESS`内部帧。</span><span class="sxs-lookup"><span data-stu-id="146ab-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="146ab-107">返回值</span><span class="sxs-lookup"><span data-stu-id="146ab-107">Return Value</span></span>  
 <span data-ttu-id="146ab-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="146ab-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="146ab-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="146ab-109">HRESULT</span></span>|<span data-ttu-id="146ab-110">描述</span><span class="sxs-lookup"><span data-stu-id="146ab-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="146ab-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="146ab-111">S_OK</span></span>|<span data-ttu-id="146ab-112">成功地返回内部帧的地址。</span><span class="sxs-lookup"><span data-stu-id="146ab-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="146ab-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="146ab-113">E_FAIL</span></span>|<span data-ttu-id="146ab-114">不会返回内部帧的地址。</span><span class="sxs-lookup"><span data-stu-id="146ab-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="146ab-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="146ab-115">E_INVALIDARG</span></span>|`pAddress` <span data-ttu-id="146ab-116">是`null`。</span><span class="sxs-lookup"><span data-stu-id="146ab-116">is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="146ab-117">备注</span><span class="sxs-lookup"><span data-stu-id="146ab-117">Remarks</span></span>  
 <span data-ttu-id="146ab-118">中返回的值`pAddress`可用于确定相对于堆栈上的其他框架的内部帧的位置。</span><span class="sxs-lookup"><span data-stu-id="146ab-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="146ab-119">即使在基于 IA-64 的计算机上的内部帧位于堆栈仅，并且没有与后备存储区没有对应的指针。</span><span class="sxs-lookup"><span data-stu-id="146ab-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="146ab-120">要求</span><span class="sxs-lookup"><span data-stu-id="146ab-120">Requirements</span></span>  
 <span data-ttu-id="146ab-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="146ab-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="146ab-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="146ab-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="146ab-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="146ab-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="146ab-124">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="146ab-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="146ab-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="146ab-125">See also</span></span>

- [<span data-ttu-id="146ab-126">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="146ab-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="146ab-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="146ab-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="146ab-128">调试</span><span class="sxs-lookup"><span data-stu-id="146ab-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
