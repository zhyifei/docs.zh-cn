---
title: ICorDebugAssembly 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd60defc1c003fa4b235ddcb0a78b9a819b1b0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198018"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="a0b6f-102">ICorDebugAssembly 接口</span><span class="sxs-lookup"><span data-stu-id="a0b6f-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="a0b6f-103">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="a0b6f-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0b6f-104">方法</span><span class="sxs-lookup"><span data-stu-id="a0b6f-104">Methods</span></span>  
  
|<span data-ttu-id="a0b6f-105">方法</span><span class="sxs-lookup"><span data-stu-id="a0b6f-105">Method</span></span>|<span data-ttu-id="a0b6f-106">描述</span><span class="sxs-lookup"><span data-stu-id="a0b6f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0b6f-107">EnumerateModules 方法</span><span class="sxs-lookup"><span data-stu-id="a0b6f-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="a0b6f-108">获取包含在程序集中的模块的枚举器。</span><span class="sxs-lookup"><span data-stu-id="a0b6f-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="a0b6f-109">GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="a0b6f-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="a0b6f-110">获取包含此应用程序域的接口指针`ICorDebugAssembly`实例。</span><span class="sxs-lookup"><span data-stu-id="a0b6f-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="a0b6f-111">GetCodeBase 方法</span><span class="sxs-lookup"><span data-stu-id="a0b6f-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="a0b6f-112">未实现当前版本的.NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="a0b6f-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="a0b6f-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="a0b6f-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="a0b6f-114">获取程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="a0b6f-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="a0b6f-115">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="a0b6f-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="a0b6f-116">获取在其中运行该程序集的 ICorDebugProcess 实例。</span><span class="sxs-lookup"><span data-stu-id="a0b6f-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0b6f-117">备注</span><span class="sxs-lookup"><span data-stu-id="a0b6f-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0b6f-118">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a0b6f-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b6f-119">要求</span><span class="sxs-lookup"><span data-stu-id="a0b6f-119">Requirements</span></span>  
 <span data-ttu-id="a0b6f-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0b6f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b6f-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0b6f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0b6f-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0b6f-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a0b6f-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a0b6f-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a0b6f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0b6f-124">See also</span></span>

- [<span data-ttu-id="a0b6f-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="a0b6f-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
