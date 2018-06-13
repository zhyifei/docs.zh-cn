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
ms.openlocfilehash: 9d02a68e80e34be906e9fe09f3457a0f2214c6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405062"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="058f7-102">ICorDebugChain::GetReason 方法</span><span class="sxs-lookup"><span data-stu-id="058f7-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="058f7-103">获取此调用链的生成的原因。</span><span class="sxs-lookup"><span data-stu-id="058f7-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="058f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="058f7-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="058f7-105">参数</span><span class="sxs-lookup"><span data-stu-id="058f7-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="058f7-106">[out]指向 CorDebugChainReason 枚举，该值指示此调用链的生成的原因的值 （按位组合） 的指针。</span><span class="sxs-lookup"><span data-stu-id="058f7-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="058f7-107">要求</span><span class="sxs-lookup"><span data-stu-id="058f7-107">Requirements</span></span>  
 <span data-ttu-id="058f7-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="058f7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="058f7-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="058f7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="058f7-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="058f7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="058f7-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="058f7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
