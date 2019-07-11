---
title: ICorDebugAppDomain::EnumerateSteppers 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea2c72a91aaa09d1c2d0e0944b73beb9ea313d0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738024"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="59b5f-102">ICorDebugAppDomain::EnumerateSteppers 方法</span><span class="sxs-lookup"><span data-stu-id="59b5f-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="59b5f-103">获取可枚举所有活动分档应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="59b5f-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b5f-104">语法</span><span class="sxs-lookup"><span data-stu-id="59b5f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59b5f-105">参数</span><span class="sxs-lookup"><span data-stu-id="59b5f-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="59b5f-106">[out]指向一个 ICorDebugStepperEnum 对象，它在应用程序域中的所有活动分档的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="59b5f-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b5f-107">要求</span><span class="sxs-lookup"><span data-stu-id="59b5f-107">Requirements</span></span>  
 <span data-ttu-id="59b5f-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="59b5f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b5f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59b5f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59b5f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59b5f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59b5f-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59b5f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
