---
title: ICorDebugLoadedModule 接口
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e91dda9cbc5957768e98db2b2a9e1026d94c03e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946278"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="ac6f1-102">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="ac6f1-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="ac6f1-103">提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="ac6f1-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac6f1-104">方法</span><span class="sxs-lookup"><span data-stu-id="ac6f1-104">Methods</span></span>  
  
|<span data-ttu-id="ac6f1-105">方法</span><span class="sxs-lookup"><span data-stu-id="ac6f1-105">Method</span></span>|<span data-ttu-id="ac6f1-106">描述</span><span class="sxs-lookup"><span data-stu-id="ac6f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac6f1-107">GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="ac6f1-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="ac6f1-108">获取已加载模块的基址。</span><span class="sxs-lookup"><span data-stu-id="ac6f1-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="ac6f1-109">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="ac6f1-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="ac6f1-110">获取加载模块的名称。</span><span class="sxs-lookup"><span data-stu-id="ac6f1-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="ac6f1-111">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="ac6f1-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="ac6f1-112">获取加载模块的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ac6f1-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac6f1-113">备注</span><span class="sxs-lookup"><span data-stu-id="ac6f1-113">Remarks</span></span>  
 <span data-ttu-id="ac6f1-114">`ICorDebugLoadedModule` 接口由调试器实现并且被 CLR 调试接口使用，以便从调试器中获取有关加载的模块的信息。</span><span class="sxs-lookup"><span data-stu-id="ac6f1-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac6f1-115">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ac6f1-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ac6f1-116">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="ac6f1-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac6f1-117">要求</span><span class="sxs-lookup"><span data-stu-id="ac6f1-117">Requirements</span></span>  
 <span data-ttu-id="ac6f1-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac6f1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac6f1-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac6f1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac6f1-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac6f1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac6f1-121">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac6f1-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6f1-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac6f1-122">See also</span></span>

- [<span data-ttu-id="ac6f1-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="ac6f1-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ac6f1-124">调试</span><span class="sxs-lookup"><span data-stu-id="ac6f1-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
