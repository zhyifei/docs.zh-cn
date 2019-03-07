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
ms.openlocfilehash: 48650a370f7d15724e20850e9d3b47dc8215f960
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498349"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="c4c74-102">ICorDebugChain::GetReason 方法</span><span class="sxs-lookup"><span data-stu-id="c4c74-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="c4c74-103">获取生成此调用链的原因。</span><span class="sxs-lookup"><span data-stu-id="c4c74-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c74-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4c74-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4c74-105">参数</span><span class="sxs-lookup"><span data-stu-id="c4c74-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="c4c74-106">[out]指向表示此调用链生成原因 CorDebugChainReason 枚举值 （按位组合） 的指针。</span><span class="sxs-lookup"><span data-stu-id="c4c74-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4c74-107">要求</span><span class="sxs-lookup"><span data-stu-id="c4c74-107">Requirements</span></span>  
 <span data-ttu-id="c4c74-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c74-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4c74-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4c74-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4c74-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4c74-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4c74-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4c74-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
