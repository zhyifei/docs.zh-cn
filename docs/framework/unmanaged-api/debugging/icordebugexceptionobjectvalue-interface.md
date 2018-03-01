---
title: "ICorDebugExceptionObjectValue 接口"
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
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6ee743a5e3e28b5d8b864f325239725ca6c0042
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="9d645-102">ICorDebugExceptionObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="9d645-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="9d645-103">扩展"ICorDebugObjectValue"接口，以提供来自托管的异常对象的堆栈跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="9d645-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d645-104">方法</span><span class="sxs-lookup"><span data-stu-id="9d645-104">Methods</span></span>  
  
|<span data-ttu-id="9d645-105">方法</span><span class="sxs-lookup"><span data-stu-id="9d645-105">Method</span></span>|<span data-ttu-id="9d645-106">描述</span><span class="sxs-lookup"><span data-stu-id="9d645-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d645-107">EnumerateExceptionCallStack 方法</span><span class="sxs-lookup"><span data-stu-id="9d645-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="9d645-108">到嵌入在异常对象的调用堆栈中获取一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="9d645-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d645-109">备注</span><span class="sxs-lookup"><span data-stu-id="9d645-109">Remarks</span></span>  
 <span data-ttu-id="9d645-110">调用`QueryInterface`将成功执行派生自的托管对象<xref:System.Exception?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="9d645-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d645-111">惠?</span><span class="sxs-lookup"><span data-stu-id="9d645-111">Requirements</span></span>  
 <span data-ttu-id="9d645-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d645-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d645-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d645-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d645-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d645-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d645-115">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d645-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d645-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d645-116">See Also</span></span>  
 [<span data-ttu-id="9d645-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="9d645-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9d645-118">调试</span><span class="sxs-lookup"><span data-stu-id="9d645-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
