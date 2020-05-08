---
title: ICorDebugChain::GetReason 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
ms.openlocfilehash: 94672c88864efc431acde8f29e406f4fbbc644ee
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894550"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="15b10-102">ICorDebugChain::GetReason 方法</span><span class="sxs-lookup"><span data-stu-id="15b10-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="15b10-103">获取此调用链的 genesis 的原因。</span><span class="sxs-lookup"><span data-stu-id="15b10-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b10-104">语法</span><span class="sxs-lookup"><span data-stu-id="15b10-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15b10-105">参数</span><span class="sxs-lookup"><span data-stu-id="15b10-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="15b10-106">弄一个指针，指向 CorDebugChainReason 枚举的值（按位组合），该枚举指示此调用链的 genesis 的原因。</span><span class="sxs-lookup"><span data-stu-id="15b10-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15b10-107">要求</span><span class="sxs-lookup"><span data-stu-id="15b10-107">Requirements</span></span>  
 <span data-ttu-id="15b10-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15b10-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b10-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15b10-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15b10-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15b10-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15b10-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15b10-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
