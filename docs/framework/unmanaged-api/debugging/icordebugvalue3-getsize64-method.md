---
title: "ICorDebugValue3::GetSize64 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4eb0c4691b82bdfaecb97c5969a942c113987c04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="a2cb1-102">ICorDebugValue3::GetSize64 方法</span><span class="sxs-lookup"><span data-stu-id="a2cb1-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="a2cb1-103">获取以字节为单位，此大小， [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="a2cb1-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2cb1-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2cb1-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2cb1-105">参数</span><span class="sxs-lookup"><span data-stu-id="a2cb1-105">Parameters</span></span>  
 <span data-ttu-id="a2cb1-106">pSize</span><span class="sxs-lookup"><span data-stu-id="a2cb1-106">pSize</span></span>  
 <span data-ttu-id="a2cb1-107">[out]指向的大小，以字节为单位，此对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a2cb1-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2cb1-108">备注</span><span class="sxs-lookup"><span data-stu-id="a2cb1-108">Remarks</span></span>  
 <span data-ttu-id="a2cb1-109">如果此值的类型是引用类型，此方法将返回指针的大小，而不是对象的大小。</span><span class="sxs-lookup"><span data-stu-id="a2cb1-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="a2cb1-110">`ICorDebugValue3::GetSize`方法不同于[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)其输出参数的类型中的方法。</span><span class="sxs-lookup"><span data-stu-id="a2cb1-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="a2cb1-111">在[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)，输出参数是`ULONG32`; 在`ICorDebugValue3::GetSize`，它是`ULONG64`。</span><span class="sxs-lookup"><span data-stu-id="a2cb1-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="a2cb1-112">这使[ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)接口报告的大小超过 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="a2cb1-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2cb1-113">惠?</span><span class="sxs-lookup"><span data-stu-id="a2cb1-113">Requirements</span></span>  
 <span data-ttu-id="a2cb1-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2cb1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2cb1-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2cb1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2cb1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2cb1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2cb1-117">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2cb1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2cb1-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2cb1-118">See Also</span></span>  
 [<span data-ttu-id="a2cb1-119">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="a2cb1-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="a2cb1-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="a2cb1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
