---
title: "ICorDebugHeapValue 接口 1"
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
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2ab132b73369526204f8fd811e1567b07b4a9b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="8d7a6-102">ICorDebugHeapValue 接口 1</span><span class="sxs-lookup"><span data-stu-id="8d7a6-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="8d7a6-103">"ICorDebugValue"，它表示由公共语言运行时 (CLR) 垃圾回收器收集对象的子类。</span><span class="sxs-lookup"><span data-stu-id="8d7a6-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d7a6-104">方法</span><span class="sxs-lookup"><span data-stu-id="8d7a6-104">Methods</span></span>  
  
|<span data-ttu-id="8d7a6-105">方法</span><span class="sxs-lookup"><span data-stu-id="8d7a6-105">Method</span></span>|<span data-ttu-id="8d7a6-106">描述</span><span class="sxs-lookup"><span data-stu-id="8d7a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d7a6-107">CreateRelocBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="8d7a6-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="8d7a6-108">未实现。</span><span class="sxs-lookup"><span data-stu-id="8d7a6-108">Not implemented.</span></span>|  
|[<span data-ttu-id="8d7a6-109">IsValid 方法</span><span class="sxs-lookup"><span data-stu-id="8d7a6-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="8d7a6-110">获取一个值，该值指示对象是否表示由此`ICorDebugHeapValue`是否有效，或者已被垃圾回收器回收。</span><span class="sxs-lookup"><span data-stu-id="8d7a6-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="8d7a6-111">.NET Framework 2.0 版中，此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="8d7a6-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d7a6-112">备注</span><span class="sxs-lookup"><span data-stu-id="8d7a6-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d7a6-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8d7a6-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d7a6-114">惠?</span><span class="sxs-lookup"><span data-stu-id="8d7a6-114">Requirements</span></span>  
 <span data-ttu-id="8d7a6-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7a6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d7a6-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d7a6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d7a6-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d7a6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d7a6-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d7a6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d7a6-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d7a6-119">See Also</span></span>  
    
    
    
 [<span data-ttu-id="8d7a6-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="8d7a6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
