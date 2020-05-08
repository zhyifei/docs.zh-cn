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
ms.openlocfilehash: d9e2236b944137de82bb056820f81014febfcc5f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894901"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="28f50-102">ICorDebugAssembly 接口</span><span class="sxs-lookup"><span data-stu-id="28f50-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="28f50-103">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="28f50-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28f50-104">方法</span><span class="sxs-lookup"><span data-stu-id="28f50-104">Methods</span></span>  
  
|<span data-ttu-id="28f50-105">方法</span><span class="sxs-lookup"><span data-stu-id="28f50-105">Method</span></span>|<span data-ttu-id="28f50-106">说明</span><span class="sxs-lookup"><span data-stu-id="28f50-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28f50-107">EnumerateModules 方法</span><span class="sxs-lookup"><span data-stu-id="28f50-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="28f50-108">获取包含在程序集中的模块的枚举器。</span><span class="sxs-lookup"><span data-stu-id="28f50-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="28f50-109">GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="28f50-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="28f50-110">获取一个接口指针，该指针指向包含此`ICorDebugAssembly`实例的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="28f50-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="28f50-111">GetCodeBase 方法</span><span class="sxs-lookup"><span data-stu-id="28f50-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="28f50-112">未在 .NET Framework 的当前版本中实现。</span><span class="sxs-lookup"><span data-stu-id="28f50-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="28f50-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="28f50-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="28f50-114">获取程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="28f50-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="28f50-115">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="28f50-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="28f50-116">获取在其中运行程序集的 ICorDebugProcess 实例。</span><span class="sxs-lookup"><span data-stu-id="28f50-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28f50-117">备注</span><span class="sxs-lookup"><span data-stu-id="28f50-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28f50-118">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="28f50-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f50-119">要求</span><span class="sxs-lookup"><span data-stu-id="28f50-119">Requirements</span></span>  
 <span data-ttu-id="28f50-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28f50-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28f50-121">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28f50-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28f50-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28f50-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28f50-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28f50-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f50-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28f50-124">See also</span></span>

- [<span data-ttu-id="28f50-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="28f50-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
