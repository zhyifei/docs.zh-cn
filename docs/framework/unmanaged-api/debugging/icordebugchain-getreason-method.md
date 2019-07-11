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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e5120b5fddf621d6f4c684c4c432fda4f5c0117
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745254"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="103cc-102">ICorDebugChain::GetReason 方法</span><span class="sxs-lookup"><span data-stu-id="103cc-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="103cc-103">获取生成此调用链的原因。</span><span class="sxs-lookup"><span data-stu-id="103cc-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="103cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="103cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="103cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="103cc-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="103cc-106">[out]指向表示此调用链生成原因 CorDebugChainReason 枚举值 （按位组合） 的指针。</span><span class="sxs-lookup"><span data-stu-id="103cc-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="103cc-107">要求</span><span class="sxs-lookup"><span data-stu-id="103cc-107">Requirements</span></span>  
 <span data-ttu-id="103cc-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="103cc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="103cc-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="103cc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="103cc-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="103cc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="103cc-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="103cc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
