---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes 方法
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36e6313ae7b4c67a20bee6d2a76a4ed1da84acbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749808"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="6ec6b-102">ICorDebugComObjectValue::GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="6ec6b-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="6ec6b-103">已强制转换为或用作当前对象的接口类型提供的枚举器。</span><span class="sxs-lookup"><span data-stu-id="6ec6b-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec6b-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ec6b-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ec6b-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ec6b-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="6ec6b-106">[in]一个值，指示该方法是否仅返回[!INCLUDE[wrt](../../../../includes/wrt-md.md)]接口 (`IInspectable`接口) 或所有缓存的运行时可调用包装 (RCW) 的 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="6ec6b-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="6ec6b-107">[out]指向提供 ICorDebugType 对象表示缓存的接口类型的访问的 ICorDebugTypeEnum 枚举器的地址的筛选根据`bIInspectableOnly`。</span><span class="sxs-lookup"><span data-stu-id="6ec6b-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ec6b-108">备注</span><span class="sxs-lookup"><span data-stu-id="6ec6b-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec6b-109">要求</span><span class="sxs-lookup"><span data-stu-id="6ec6b-109">Requirements</span></span>  
 <span data-ttu-id="6ec6b-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec6b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ec6b-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ec6b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ec6b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ec6b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ec6b-113">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ec6b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec6b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ec6b-114">See also</span></span>

- [<span data-ttu-id="6ec6b-115">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="6ec6b-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="6ec6b-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="6ec6b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
