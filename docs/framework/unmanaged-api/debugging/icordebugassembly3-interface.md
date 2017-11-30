---
title: "“ICor调试程序集3”接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9ed476746e627be987e6307bd367f0d16374de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="a15b9-102">“ICor调试程序集3”接口</span><span class="sxs-lookup"><span data-stu-id="a15b9-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="a15b9-103">合理扩展 ICorDebugAssembly 接口以提供为容器程序集及其包含的程序集的支持。</span><span class="sxs-lookup"><span data-stu-id="a15b9-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a15b9-104">方法</span><span class="sxs-lookup"><span data-stu-id="a15b9-104">Methods</span></span>  
  
|<span data-ttu-id="a15b9-105">方法</span><span class="sxs-lookup"><span data-stu-id="a15b9-105">Method</span></span>|<span data-ttu-id="a15b9-106">描述</span><span class="sxs-lookup"><span data-stu-id="a15b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a15b9-107">EnumerateContainedAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="a15b9-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="a15b9-108">获取该程序集中所包含的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="a15b9-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="a15b9-109">GetContainerAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="a15b9-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="a15b9-110">返回该 `ICorDebugAssembly3` 对象的容器程序集。</span><span class="sxs-lookup"><span data-stu-id="a15b9-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a15b9-111">备注</span><span class="sxs-lookup"><span data-stu-id="a15b9-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a15b9-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a15b9-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="a15b9-113">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="a15b9-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a15b9-114">要求</span><span class="sxs-lookup"><span data-stu-id="a15b9-114">Requirements</span></span>  
 <span data-ttu-id="a15b9-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a15b9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a15b9-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a15b9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a15b9-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a15b9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a15b9-118">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a15b9-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a15b9-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a15b9-119">See Also</span></span>  
 [<span data-ttu-id="a15b9-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="a15b9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a15b9-121">调试</span><span class="sxs-lookup"><span data-stu-id="a15b9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
