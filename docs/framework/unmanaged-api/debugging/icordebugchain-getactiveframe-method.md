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
ms.openlocfilehash: c14b48a29993a65a0a0ab9fcb63bcb1e0d882042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645365"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="dd0b1-102">ICorDebugChain::GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="dd0b1-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="dd0b1-103">获取活动 (即，最新) 链上的帧。</span><span class="sxs-lookup"><span data-stu-id="dd0b1-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd0b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd0b1-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd0b1-105">参数</span><span class="sxs-lookup"><span data-stu-id="dd0b1-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="dd0b1-106">[out]指向一个 ICorDebugFrame 对象，表示活动的地址的指针 (即，最新) 链上的帧。</span><span class="sxs-lookup"><span data-stu-id="dd0b1-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd0b1-107">备注</span><span class="sxs-lookup"><span data-stu-id="dd0b1-107">Remarks</span></span>  
 <span data-ttu-id="dd0b1-108">如果没有托管的堆栈帧可用，`ppFrame`设置为 null。</span><span class="sxs-lookup"><span data-stu-id="dd0b1-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="dd0b1-109">如果活动帧不可用，也可成功调用和`ppFrame`将为 null。</span><span class="sxs-lookup"><span data-stu-id="dd0b1-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="dd0b1-110">活动帧不会适用于链 CHAIN_ENTER_UNMANAGED，由于启动和启动 CHAIN_CLASS_INIT 由于某些链。</span><span class="sxs-lookup"><span data-stu-id="dd0b1-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="dd0b1-111">请参阅 CorDebugChainReason 枚举。</span><span class="sxs-lookup"><span data-stu-id="dd0b1-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd0b1-112">要求</span><span class="sxs-lookup"><span data-stu-id="dd0b1-112">Requirements</span></span>  
 <span data-ttu-id="dd0b1-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd0b1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd0b1-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd0b1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd0b1-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd0b1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd0b1-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd0b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
