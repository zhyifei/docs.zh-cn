---
title: "ICorDebugAssembly 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly
helpviewer_keywords: ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6331c00c2be0805afb56028e9e1a13cd11168cf1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="61d13-102">ICorDebugAssembly 接口 1</span><span class="sxs-lookup"><span data-stu-id="61d13-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="61d13-103">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="61d13-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61d13-104">方法</span><span class="sxs-lookup"><span data-stu-id="61d13-104">Methods</span></span>  
  
|<span data-ttu-id="61d13-105">方法</span><span class="sxs-lookup"><span data-stu-id="61d13-105">Method</span></span>|<span data-ttu-id="61d13-106">描述</span><span class="sxs-lookup"><span data-stu-id="61d13-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61d13-107">EnumerateModules 方法</span><span class="sxs-lookup"><span data-stu-id="61d13-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="61d13-108">获取包含在程序集中的模块的枚举数。</span><span class="sxs-lookup"><span data-stu-id="61d13-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="61d13-109">GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="61d13-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="61d13-110">获取包含此应用程序域的接口指针`ICorDebugAssembly`实例。</span><span class="sxs-lookup"><span data-stu-id="61d13-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="61d13-111">GetCodeBase 方法</span><span class="sxs-lookup"><span data-stu-id="61d13-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="61d13-112">在.NET Framework 的当前版本中未实现。</span><span class="sxs-lookup"><span data-stu-id="61d13-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="61d13-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="61d13-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="61d13-114">获取程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="61d13-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="61d13-115">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="61d13-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="61d13-116">获取在其中运行该程序集的 ICorDebugProcess 实例。</span><span class="sxs-lookup"><span data-stu-id="61d13-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61d13-117">备注</span><span class="sxs-lookup"><span data-stu-id="61d13-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61d13-118">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="61d13-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61d13-119">惠?</span><span class="sxs-lookup"><span data-stu-id="61d13-119">Requirements</span></span>  
 <span data-ttu-id="61d13-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61d13-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61d13-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61d13-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61d13-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61d13-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61d13-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61d13-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d13-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="61d13-124">See Also</span></span>  
 [<span data-ttu-id="61d13-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="61d13-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
