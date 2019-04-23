---
title: “ICor调试程序集3”接口
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210303"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="37139-102">“ICor调试程序集3”接口</span><span class="sxs-lookup"><span data-stu-id="37139-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="37139-103">合理扩展 icor 调试程序集接口以便为容器程序集和其包含的程序集提供支持。</span><span class="sxs-lookup"><span data-stu-id="37139-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37139-104">方法</span><span class="sxs-lookup"><span data-stu-id="37139-104">Methods</span></span>  
  
|<span data-ttu-id="37139-105">方法</span><span class="sxs-lookup"><span data-stu-id="37139-105">Method</span></span>|<span data-ttu-id="37139-106">描述</span><span class="sxs-lookup"><span data-stu-id="37139-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37139-107">EnumerateContainedAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="37139-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="37139-108">获取该程序集中所包含的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="37139-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="37139-109">GetContainerAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="37139-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="37139-110">返回该 `ICorDebugAssembly3` 对象的容器程序集。</span><span class="sxs-lookup"><span data-stu-id="37139-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37139-111">备注</span><span class="sxs-lookup"><span data-stu-id="37139-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37139-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="37139-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="37139-113">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="37139-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37139-114">要求</span><span class="sxs-lookup"><span data-stu-id="37139-114">Requirements</span></span>  
 <span data-ttu-id="37139-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37139-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37139-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37139-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37139-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37139-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37139-118">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37139-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37139-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="37139-119">See also</span></span>

- [<span data-ttu-id="37139-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="37139-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="37139-121">调试</span><span class="sxs-lookup"><span data-stu-id="37139-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
