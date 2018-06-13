---
title: ICorDebugReferenceValue::SetValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f0c06f9b04c5f15171464b93dc93765625d6f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418137"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="85d10-102">ICorDebugReferenceValue::SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="85d10-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="85d10-103">设置指定的内存地址。</span><span class="sxs-lookup"><span data-stu-id="85d10-103">Sets the specified memory address.</span></span> <span data-ttu-id="85d10-104">也就是说，此方法会设置此 ICorDebugReferenceValue 要指向的对象。</span><span class="sxs-lookup"><span data-stu-id="85d10-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d10-105">语法</span><span class="sxs-lookup"><span data-stu-id="85d10-105">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85d10-106">参数</span><span class="sxs-lookup"><span data-stu-id="85d10-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="85d10-107">[in]A`CORDB_ADDRESS`值，该值指定此对象的地址`ICorDebugReferenceValue`点。</span><span class="sxs-lookup"><span data-stu-id="85d10-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85d10-108">要求</span><span class="sxs-lookup"><span data-stu-id="85d10-108">Requirements</span></span>  
 <span data-ttu-id="85d10-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85d10-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85d10-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85d10-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85d10-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85d10-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85d10-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85d10-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
