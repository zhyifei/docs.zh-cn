---
title: ICorDebugArrayValue::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa72f82d2fc78110fc2bee8edd265916996aa884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403141"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="1f68d-102">ICorDebugArrayValue::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="1f68d-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="1f68d-103">获取数组中的元素总数。</span><span class="sxs-lookup"><span data-stu-id="1f68d-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f68d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f68d-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f68d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f68d-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="1f68d-106">[out]指向数组中的元素总数的指针。</span><span class="sxs-lookup"><span data-stu-id="1f68d-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f68d-107">要求</span><span class="sxs-lookup"><span data-stu-id="1f68d-107">Requirements</span></span>  
 <span data-ttu-id="1f68d-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f68d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f68d-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f68d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f68d-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f68d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f68d-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f68d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
