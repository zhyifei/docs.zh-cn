---
title: "ICorDebugComObjectValue 接口"
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
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9adeec14e102ef575f24566980477a285f87ba40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="4ecfb-102">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="4ecfb-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="4ecfb-103">提供用于检索与运行时可调用包装 (RCW) 关联的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="4ecfb-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ecfb-104">方法</span><span class="sxs-lookup"><span data-stu-id="4ecfb-104">Methods</span></span>  
  
|<span data-ttu-id="4ecfb-105">方法</span><span class="sxs-lookup"><span data-stu-id="4ecfb-105">Method</span></span>|<span data-ttu-id="4ecfb-106">描述</span><span class="sxs-lookup"><span data-stu-id="4ecfb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ecfb-107">GetCachedInterfacePointers 方法</span><span class="sxs-lookup"><span data-stu-id="4ecfb-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="4ecfb-108">获取在当前 RCW 上缓存的原始接口指针。</span><span class="sxs-lookup"><span data-stu-id="4ecfb-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="4ecfb-109">GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="4ecfb-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="4ecfb-110">已到大小写形式或用作当前对象的接口类型提供的枚举器。</span><span class="sxs-lookup"><span data-stu-id="4ecfb-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ecfb-111">备注</span><span class="sxs-lookup"><span data-stu-id="4ecfb-111">Remarks</span></span>  
 <span data-ttu-id="4ecfb-112">若要检查"ICorDebugValue"接口的实例是否表示 RCW，调试器将调用`QueryInterface`上与"ICorDebugValue" `IID_ICorDebugComObjectValue`。</span><span class="sxs-lookup"><span data-stu-id="4ecfb-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ecfb-113">惠?</span><span class="sxs-lookup"><span data-stu-id="4ecfb-113">Requirements</span></span>  
 <span data-ttu-id="4ecfb-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ecfb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ecfb-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ecfb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ecfb-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ecfb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ecfb-117">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ecfb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ecfb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ecfb-118">See Also</span></span>  
 [<span data-ttu-id="4ecfb-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="4ecfb-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4ecfb-120">调试</span><span class="sxs-lookup"><span data-stu-id="4ecfb-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
