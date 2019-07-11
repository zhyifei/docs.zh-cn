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
ms.openlocfilehash: c7325e84d8fe4df9a31543426c6376d0941306fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748455"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="98210-102">ICorDebugComObjectValue::GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="98210-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="98210-103">已强制转换为或用作当前对象的接口类型提供的枚举器。</span><span class="sxs-lookup"><span data-stu-id="98210-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98210-104">语法</span><span class="sxs-lookup"><span data-stu-id="98210-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98210-105">参数</span><span class="sxs-lookup"><span data-stu-id="98210-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="98210-106">[in]一个值，指示该方法是否返回唯一的 Windows 运行时接口 (`IInspectable`接口) 或所有缓存的运行时可调用包装 (RCW) 的 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="98210-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="98210-107">[out]指向提供 ICorDebugType 对象表示缓存的接口类型的访问的 ICorDebugTypeEnum 枚举器的地址的筛选根据`bIInspectableOnly`。</span><span class="sxs-lookup"><span data-stu-id="98210-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98210-108">备注</span><span class="sxs-lookup"><span data-stu-id="98210-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98210-109">要求</span><span class="sxs-lookup"><span data-stu-id="98210-109">Requirements</span></span>  
 <span data-ttu-id="98210-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98210-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98210-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98210-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98210-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98210-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98210-113">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98210-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98210-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="98210-114">See also</span></span>

- [<span data-ttu-id="98210-115">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="98210-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="98210-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="98210-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
