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
ms.openlocfilehash: 40e64bdb35cff4e6ad6132c0806cfddd2767443c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122679"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="f7a1a-102">ICorDebugInternalFrame2::GetFrameAddress 方法</span><span class="sxs-lookup"><span data-stu-id="f7a1a-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="f7a1a-103">返回内部帧的堆栈地址。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7a1a-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7a1a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7a1a-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7a1a-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="f7a1a-106">弄指向内部框架的 `CORDB_ADDRESS` 的指针。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7a1a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f7a1a-107">Return Value</span></span>  
 <span data-ttu-id="f7a1a-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f7a1a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7a1a-109">HRESULT</span></span>|<span data-ttu-id="f7a1a-110">描述</span><span class="sxs-lookup"><span data-stu-id="f7a1a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7a1a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7a1a-111">S_OK</span></span>|<span data-ttu-id="f7a1a-112">已成功返回内部帧的地址。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="f7a1a-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7a1a-113">E_FAIL</span></span>|<span data-ttu-id="f7a1a-114">无法返回内部帧的地址。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="f7a1a-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f7a1a-115">E_INVALIDARG</span></span>|<span data-ttu-id="f7a1a-116">`pAddress` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7a1a-117">备注</span><span class="sxs-lookup"><span data-stu-id="f7a1a-117">Remarks</span></span>  
 <span data-ttu-id="f7a1a-118">`pAddress` 中返回的值可用于确定内部帧相对于堆栈上其他帧的位置。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="f7a1a-119">即使在基于 IA-64 的计算机上，内部帧也仅驻留在堆栈上，并且没有指向后备存储的相应指针。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7a1a-120">要求</span><span class="sxs-lookup"><span data-stu-id="f7a1a-120">Requirements</span></span>  
 <span data-ttu-id="f7a1a-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7a1a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7a1a-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7a1a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7a1a-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7a1a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7a1a-124">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7a1a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a1a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7a1a-125">See also</span></span>

- [<span data-ttu-id="f7a1a-126">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="f7a1a-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="f7a1a-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="f7a1a-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f7a1a-128">调试</span><span class="sxs-lookup"><span data-stu-id="f7a1a-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
