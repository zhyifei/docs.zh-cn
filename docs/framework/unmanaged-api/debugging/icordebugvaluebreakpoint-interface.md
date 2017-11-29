---
title: "ICorDebugValueBreakpoint 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValueBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValueBreakpoint
helpviewer_keywords: ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 04ce1827bbc70fc4f1406f802c3a382858b08699
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="3507d-102">ICorDebugValueBreakpoint 接口 1</span><span class="sxs-lookup"><span data-stu-id="3507d-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="3507d-103">扩展 ICorDebugBreakpoint 接口，以提供对特定值的访问。</span><span class="sxs-lookup"><span data-stu-id="3507d-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3507d-104">方法</span><span class="sxs-lookup"><span data-stu-id="3507d-104">Methods</span></span>  
  
|<span data-ttu-id="3507d-105">方法</span><span class="sxs-lookup"><span data-stu-id="3507d-105">Method</span></span>|<span data-ttu-id="3507d-106">描述</span><span class="sxs-lookup"><span data-stu-id="3507d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3507d-107">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="3507d-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="3507d-108">获取一个表示对其设置断点的对象的值的 ICorDebugValue 对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="3507d-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3507d-109">备注</span><span class="sxs-lookup"><span data-stu-id="3507d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3507d-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="3507d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3507d-111">要求</span><span class="sxs-lookup"><span data-stu-id="3507d-111">Requirements</span></span>  
 <span data-ttu-id="3507d-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3507d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3507d-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3507d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3507d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3507d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3507d-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3507d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3507d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3507d-116">See Also</span></span>  
 [<span data-ttu-id="3507d-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="3507d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
