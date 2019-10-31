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
ms.openlocfilehash: 03cb1556ee971124ed4c591f38d9f892fc7df7b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192145"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="6f255-102">ICorDebugChain::GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="6f255-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="6f255-103">获取链上的活动（即最近的）帧。</span><span class="sxs-lookup"><span data-stu-id="6f255-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f255-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f255-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f255-105">参数</span><span class="sxs-lookup"><span data-stu-id="6f255-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="6f255-106">弄指向 ICorDebugFrame 对象的地址的指针，该对象表示链上的活动（即最近的）帧。</span><span class="sxs-lookup"><span data-stu-id="6f255-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f255-107">备注</span><span class="sxs-lookup"><span data-stu-id="6f255-107">Remarks</span></span>  
 <span data-ttu-id="6f255-108">如果没有可用的托管堆栈帧，则 `ppFrame` 设置为 null。</span><span class="sxs-lookup"><span data-stu-id="6f255-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="6f255-109">如果没有可用的活动帧，则调用将成功并且 `ppFrame` 将为 null。</span><span class="sxs-lookup"><span data-stu-id="6f255-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="6f255-110">由于 CHAIN_ENTER_UNMANAGED 和由于 CHAIN_CLASS_INIT 而启动的某些链的原因，活动帧将不可用于启动的链。</span><span class="sxs-lookup"><span data-stu-id="6f255-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="6f255-111">请参阅 CorDebugChainReason 枚举。</span><span class="sxs-lookup"><span data-stu-id="6f255-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f255-112">要求</span><span class="sxs-lookup"><span data-stu-id="6f255-112">Requirements</span></span>  
 <span data-ttu-id="6f255-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6f255-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f255-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f255-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f255-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f255-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f255-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f255-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
