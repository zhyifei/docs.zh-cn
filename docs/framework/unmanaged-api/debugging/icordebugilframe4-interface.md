---
title: "ICorDebugILFrame4 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame4
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b42a2ed4e93fd5e4c662bab34b111fe0757890
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="1ac65-102">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="1ac65-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="1ac65-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="1ac65-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1ac65-104">提供使你能够访问中间语言 (IL) 代码的堆栈帧中的局部变量和代码的方法。</span><span class="sxs-lookup"><span data-stu-id="1ac65-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="1ac65-105">一个用于指定调试器是否可以访问在探查器 ReJIT 检测中添加的变量和代码的参数。</span><span class="sxs-lookup"><span data-stu-id="1ac65-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ac65-106">方法</span><span class="sxs-lookup"><span data-stu-id="1ac65-106">Methods</span></span>  
  
|<span data-ttu-id="1ac65-107">方法</span><span class="sxs-lookup"><span data-stu-id="1ac65-107">Method</span></span>|<span data-ttu-id="1ac65-108">描述</span><span class="sxs-lookup"><span data-stu-id="1ac65-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ac65-109">EnumerateLocalVariablesEx 方法</span><span class="sxs-lookup"><span data-stu-id="1ac65-109">EnumerateLocalVariablesEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="1ac65-110">返回在当前帧中可用的局部变量的列表。</span><span class="sxs-lookup"><span data-stu-id="1ac65-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="1ac65-111">GetCodeEx 方法</span><span class="sxs-lookup"><span data-stu-id="1ac65-111">GetCodeEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="1ac65-112">返回此堆栈帧正在运行的代码。</span><span class="sxs-lookup"><span data-stu-id="1ac65-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="1ac65-113">GetLocalVariableEx 方法</span><span class="sxs-lookup"><span data-stu-id="1ac65-113">GetLocalVariableEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="1ac65-114">返回 IL 帧中的局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="1ac65-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ac65-115">备注</span><span class="sxs-lookup"><span data-stu-id="1ac65-115">Remarks</span></span>  
 <span data-ttu-id="1ac65-116">这些方法提供以及由提供的功能[EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)， [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)，和[GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1ac65-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), and [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="1ac65-117">每个方法都包含一个 `flags` 参数，该参数可指定探查器的 ReJIT 请求定义的附加局部变量或代码是否可见。</span><span class="sxs-lookup"><span data-stu-id="1ac65-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ac65-118">要求</span><span class="sxs-lookup"><span data-stu-id="1ac65-118">Requirements</span></span>  
 <span data-ttu-id="1ac65-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac65-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ac65-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ac65-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ac65-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ac65-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ac65-122">**.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ac65-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ac65-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ac65-123">See Also</span></span>  
 [<span data-ttu-id="1ac65-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="1ac65-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1ac65-125">调试</span><span class="sxs-lookup"><span data-stu-id="1ac65-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
