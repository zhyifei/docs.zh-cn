---
title: "ICorDebugFunction2 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2
helpviewer_keywords: ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ac3a4cd5ec2aff1b60cd51ca33d411e5cc81eb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2-interface1"></a><span data-ttu-id="6ea69-102">ICorDebugFunction2 接口 1</span><span class="sxs-lookup"><span data-stu-id="6ea69-102">ICorDebugFunction2 Interface1</span></span>
<span data-ttu-id="6ea69-103">合理扩展 ICorDebugFunction 接口以支持仅我的代码单步执行调试，这样可以跳过非用户代码。</span><span class="sxs-lookup"><span data-stu-id="6ea69-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ea69-104">方法</span><span class="sxs-lookup"><span data-stu-id="6ea69-104">Methods</span></span>  
  
|<span data-ttu-id="6ea69-105">方法</span><span class="sxs-lookup"><span data-stu-id="6ea69-105">Method</span></span>|<span data-ttu-id="6ea69-106">描述</span><span class="sxs-lookup"><span data-stu-id="6ea69-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ea69-107">EnumerateNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="6ea69-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="6ea69-108">（尚未实现。）获取包含此 ICorDebugFunction2 对象引用的函数中的本机代码语句 ICorDebugCodeEnum 接口指针。</span><span class="sxs-lookup"><span data-stu-id="6ea69-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="6ea69-109">GetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="6ea69-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="6ea69-110">获取一个值，该值指示是否将此函数标记为用户代码。</span><span class="sxs-lookup"><span data-stu-id="6ea69-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="6ea69-111">GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="6ea69-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="6ea69-112">获取此函数的编辑并继续版本。</span><span class="sxs-lookup"><span data-stu-id="6ea69-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="6ea69-113">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="6ea69-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="6ea69-114">对于仅我的代码将标记为此函数单步执行。</span><span class="sxs-lookup"><span data-stu-id="6ea69-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ea69-115">备注</span><span class="sxs-lookup"><span data-stu-id="6ea69-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ea69-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="6ea69-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea69-117">惠?</span><span class="sxs-lookup"><span data-stu-id="6ea69-117">Requirements</span></span>  
 <span data-ttu-id="6ea69-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea69-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea69-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ea69-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ea69-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ea69-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ea69-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea69-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea69-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea69-122">See Also</span></span>  
 [<span data-ttu-id="6ea69-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="6ea69-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
