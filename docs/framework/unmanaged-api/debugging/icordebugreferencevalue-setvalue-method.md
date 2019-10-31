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
ms.openlocfilehash: 61563488bff682cc7a417296c3db8eb7e7cf965a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139322"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="e51f2-102">ICorDebugReferenceValue::SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="e51f2-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="e51f2-103">设置指定的内存地址。</span><span class="sxs-lookup"><span data-stu-id="e51f2-103">Sets the specified memory address.</span></span> <span data-ttu-id="e51f2-104">也就是说，此方法会将此 ICorDebugReferenceValue 设置为指向某个对象。</span><span class="sxs-lookup"><span data-stu-id="e51f2-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e51f2-105">语法</span><span class="sxs-lookup"><span data-stu-id="e51f2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e51f2-106">参数</span><span class="sxs-lookup"><span data-stu-id="e51f2-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="e51f2-107">中一个 `CORDB_ADDRESS` 值，该值指定此 `ICorDebugReferenceValue` 指向的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="e51f2-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e51f2-108">要求</span><span class="sxs-lookup"><span data-stu-id="e51f2-108">Requirements</span></span>  
 <span data-ttu-id="e51f2-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e51f2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e51f2-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e51f2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e51f2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e51f2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e51f2-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e51f2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
