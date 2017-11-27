---
title: "ICorDebugComObjectValue::GetCachedInterfaceTypes 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location: mscordbi.dll
f1_keywords: ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2150e75b5b9f09424f08c29345d5d139c1673afa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="c317b-102">ICorDebugComObjectValue::GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="c317b-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="c317b-103">已强制转换为或用作当前对象的接口类型提供的枚举器。</span><span class="sxs-lookup"><span data-stu-id="c317b-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c317b-104">语法</span><span class="sxs-lookup"><span data-stu-id="c317b-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c317b-105">参数</span><span class="sxs-lookup"><span data-stu-id="c317b-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="c317b-106">[in]一个值，指示该方法仅返回[!INCLUDE[wrt](../../../../includes/wrt-md.md)]接口 (`IInspectable`接口) 或缓存由运行时可调用包装 (RCW) 的所有 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="c317b-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="c317b-107">[out]ICorDebugTypeEnum 枚举器可访问 ICorDebugType 表示缓存的接口类型的对象的地址指针筛选根据`bIInspectableOnly`。</span><span class="sxs-lookup"><span data-stu-id="c317b-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c317b-108">备注</span><span class="sxs-lookup"><span data-stu-id="c317b-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c317b-109">要求</span><span class="sxs-lookup"><span data-stu-id="c317b-109">Requirements</span></span>  
 <span data-ttu-id="c317b-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c317b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c317b-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c317b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c317b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c317b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c317b-113">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c317b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c317b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c317b-114">See Also</span></span>  
 [<span data-ttu-id="c317b-115">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="c317b-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="c317b-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="c317b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
