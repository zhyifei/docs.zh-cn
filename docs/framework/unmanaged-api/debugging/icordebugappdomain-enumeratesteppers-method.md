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
ms.openlocfilehash: 7bf3aa6d883dffece6ba89d41005499cc6206906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401286"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="1d9ec-102">ICorDebugAppDomain::EnumerateSteppers 方法</span><span class="sxs-lookup"><span data-stu-id="1d9ec-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="1d9ec-103">应用程序域中获取所有活动分档的枚举数。</span><span class="sxs-lookup"><span data-stu-id="1d9ec-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d9ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d9ec-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d9ec-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d9ec-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="1d9ec-106">[out]指向的地址是应用程序域中的所有活动分档的枚举器的 ICorDebugStepperEnum 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1d9ec-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d9ec-107">要求</span><span class="sxs-lookup"><span data-stu-id="1d9ec-107">Requirements</span></span>  
 <span data-ttu-id="1d9ec-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d9ec-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d9ec-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d9ec-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d9ec-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d9ec-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d9ec-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9ec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
