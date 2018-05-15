---
title: ICorDebugChain::GetActiveFrame 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a104d4d3cc74a6c1cb343818c9b0b3e8978b97df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="d7603-102">ICorDebugChain::GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="d7603-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="d7603-103">获取活动 (即，最新) 链上的帧。</span><span class="sxs-lookup"><span data-stu-id="d7603-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7603-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7603-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7603-105">参数</span><span class="sxs-lookup"><span data-stu-id="d7603-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="d7603-106">[out]指向一个 ICorDebugFrame 对象，表示活动的地址的指针 (即，最新) 链上的帧。</span><span class="sxs-lookup"><span data-stu-id="d7603-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7603-107">备注</span><span class="sxs-lookup"><span data-stu-id="d7603-107">Remarks</span></span>  
 <span data-ttu-id="d7603-108">如果没有托管的堆栈帧不可用，`ppFrame`设置为 null。</span><span class="sxs-lookup"><span data-stu-id="d7603-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="d7603-109">如果活动帧不可用，则调用将成功和`ppFrame`将为 null。</span><span class="sxs-lookup"><span data-stu-id="d7603-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="d7603-110">活动帧将不可用为链由于 CHAIN_ENTER_UNMANAGED，启动和为启动 CHAIN_CLASS_INIT 由于某些链。</span><span class="sxs-lookup"><span data-stu-id="d7603-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="d7603-111">请参阅 CorDebugChainReason 枚举。</span><span class="sxs-lookup"><span data-stu-id="d7603-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7603-112">要求</span><span class="sxs-lookup"><span data-stu-id="d7603-112">Requirements</span></span>  
 <span data-ttu-id="d7603-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7603-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7603-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7603-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7603-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7603-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7603-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7603-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
