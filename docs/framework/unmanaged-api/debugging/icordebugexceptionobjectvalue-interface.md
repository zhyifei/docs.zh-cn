---
title: ICorDebugExceptionObjectValue 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1baae7d7867b0cbb227af72fcc505a5cadfa4df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511624"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="cbe8d-102">ICorDebugExceptionObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="cbe8d-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="cbe8d-103">扩展了"ICorDebugObjectValue"接口，以提供从托管的异常对象的堆栈跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="cbe8d-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cbe8d-104">方法</span><span class="sxs-lookup"><span data-stu-id="cbe8d-104">Methods</span></span>  
  
|<span data-ttu-id="cbe8d-105">方法</span><span class="sxs-lookup"><span data-stu-id="cbe8d-105">Method</span></span>|<span data-ttu-id="cbe8d-106">描述</span><span class="sxs-lookup"><span data-stu-id="cbe8d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cbe8d-107">EnumerateExceptionCallStack 方法</span><span class="sxs-lookup"><span data-stu-id="cbe8d-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="cbe8d-108">获取嵌入异常对象中的调用堆栈的枚举器。</span><span class="sxs-lookup"><span data-stu-id="cbe8d-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbe8d-109">备注</span><span class="sxs-lookup"><span data-stu-id="cbe8d-109">Remarks</span></span>  
 <span data-ttu-id="cbe8d-110">在调用`QueryInterface`派生的托管对象将会成功<xref:System.Exception?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="cbe8d-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbe8d-111">要求</span><span class="sxs-lookup"><span data-stu-id="cbe8d-111">Requirements</span></span>  
 <span data-ttu-id="cbe8d-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe8d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbe8d-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbe8d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbe8d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbe8d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbe8d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbe8d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe8d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe8d-116">See also</span></span>
- [<span data-ttu-id="cbe8d-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="cbe8d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cbe8d-118">调试</span><span class="sxs-lookup"><span data-stu-id="cbe8d-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

