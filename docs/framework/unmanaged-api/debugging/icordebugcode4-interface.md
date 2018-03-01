---
title: "ICorDebugCode4 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30c0599e183d51030ac5b063a2aca4352ad95eca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="0ed06-102">ICorDebugCode4 接口</span><span class="sxs-lookup"><span data-stu-id="0ed06-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="0ed06-103">提供使调试器能够枚举的本地变量和函数中的自变量的方法。</span><span class="sxs-lookup"><span data-stu-id="0ed06-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ed06-104">方法</span><span class="sxs-lookup"><span data-stu-id="0ed06-104">Methods</span></span>  
  
|<span data-ttu-id="0ed06-105">方法</span><span class="sxs-lookup"><span data-stu-id="0ed06-105">Method</span></span>|<span data-ttu-id="0ed06-106">描述</span><span class="sxs-lookup"><span data-stu-id="0ed06-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ed06-107">EnumerateVariableHomes 方法</span><span class="sxs-lookup"><span data-stu-id="0ed06-107">EnumerateVariableHomes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="0ed06-108">获取可枚举的本地变量和自变量的函数中。</span><span class="sxs-lookup"><span data-stu-id="0ed06-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ed06-109">备注</span><span class="sxs-lookup"><span data-stu-id="0ed06-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ed06-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="0ed06-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ed06-111">惠?</span><span class="sxs-lookup"><span data-stu-id="0ed06-111">Requirements</span></span>  
 <span data-ttu-id="0ed06-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed06-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ed06-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ed06-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ed06-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ed06-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ed06-115">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ed06-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed06-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ed06-116">See Also</span></span>  
    
    
 [<span data-ttu-id="0ed06-117">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="0ed06-117">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="0ed06-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="0ed06-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
