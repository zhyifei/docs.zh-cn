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
ms.openlocfilehash: 2f67188539d5ad5523c255fbc663e990e1b8245f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894685"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="9e359-102">ICorDebugChain::GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="9e359-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="9e359-103">获取链上的活动（即最近的）帧。</span><span class="sxs-lookup"><span data-stu-id="9e359-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e359-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e359-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e359-105">参数</span><span class="sxs-lookup"><span data-stu-id="9e359-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="9e359-106">弄指向 ICorDebugFrame 对象的地址的指针，该对象表示链上的活动（即最近的）帧。</span><span class="sxs-lookup"><span data-stu-id="9e359-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e359-107">备注</span><span class="sxs-lookup"><span data-stu-id="9e359-107">Remarks</span></span>  
 <span data-ttu-id="9e359-108">如果没有可用的托管堆栈帧， `ppFrame`则将设置为 null。</span><span class="sxs-lookup"><span data-stu-id="9e359-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="9e359-109">如果活动帧不可用，则调用将成功，并且`ppFrame`将为 null。</span><span class="sxs-lookup"><span data-stu-id="9e359-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="9e359-110">由于 CHAIN_ENTER_UNMANAGED，活动帧将不可用于发起的链，并且由于 CHAIN_CLASS_INIT 而导致的某些链启动了。</span><span class="sxs-lookup"><span data-stu-id="9e359-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="9e359-111">请参阅 CorDebugChainReason 枚举。</span><span class="sxs-lookup"><span data-stu-id="9e359-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e359-112">要求</span><span class="sxs-lookup"><span data-stu-id="9e359-112">Requirements</span></span>  
 <span data-ttu-id="9e359-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e359-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e359-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e359-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e359-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e359-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e359-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e359-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
