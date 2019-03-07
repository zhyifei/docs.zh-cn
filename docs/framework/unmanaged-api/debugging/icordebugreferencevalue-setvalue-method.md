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
ms.openlocfilehash: 59ef7bf8f17e79c9ae7b80dd314a5afce7fa9584
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474171"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="53459-102">ICorDebugReferenceValue::SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="53459-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="53459-103">设置指定的内存地址。</span><span class="sxs-lookup"><span data-stu-id="53459-103">Sets the specified memory address.</span></span> <span data-ttu-id="53459-104">也就是说，此方法设置此 ICorDebugReferenceValue 要指向的对象。</span><span class="sxs-lookup"><span data-stu-id="53459-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53459-105">语法</span><span class="sxs-lookup"><span data-stu-id="53459-105">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53459-106">参数</span><span class="sxs-lookup"><span data-stu-id="53459-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="53459-107">[in]一个`CORDB_ADDRESS`值，该值指定此对象的地址`ICorDebugReferenceValue`点。</span><span class="sxs-lookup"><span data-stu-id="53459-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53459-108">要求</span><span class="sxs-lookup"><span data-stu-id="53459-108">Requirements</span></span>  
 <span data-ttu-id="53459-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53459-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53459-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53459-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53459-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53459-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53459-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53459-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
