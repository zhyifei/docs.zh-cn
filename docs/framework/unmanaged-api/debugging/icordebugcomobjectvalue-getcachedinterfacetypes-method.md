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
ms.openlocfilehash: f720b06581ac60c8bd68dc5e85f15843fd9425f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788907"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="75596-102">ICorDebugComObjectValue::GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="75596-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="75596-103">为当前对象已强制转换为或用作的接口类型提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="75596-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75596-104">语法</span><span class="sxs-lookup"><span data-stu-id="75596-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75596-105">参数</span><span class="sxs-lookup"><span data-stu-id="75596-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="75596-106">中一个值，该值指示方法是只返回 Windows 运行时接口（`IInspectable` 接口），还是返回由运行时可调用包装（RCW）缓存的所有 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="75596-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="75596-107">弄指向 ICorDebugTypeEnum 枚举器地址的指针，该枚举数提供对 ICorDebugType 对象（表示根据 `bIInspectableOnly`筛选的缓存接口类型）的访问。</span><span class="sxs-lookup"><span data-stu-id="75596-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75596-108">备注</span><span class="sxs-lookup"><span data-stu-id="75596-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75596-109">需求</span><span class="sxs-lookup"><span data-stu-id="75596-109">Requirements</span></span>  
 <span data-ttu-id="75596-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75596-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75596-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75596-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75596-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75596-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75596-113">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75596-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75596-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75596-114">See also</span></span>

- [<span data-ttu-id="75596-115">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="75596-115">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="75596-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="75596-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
