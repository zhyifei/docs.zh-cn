---
title: ICorDebugStaticFieldSymbol 接口
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4e245e96ac9d47db10072e50a5b3c516d5dd27
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962683"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="4de81-102">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="4de81-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="4de81-103">表示某个静态字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="4de81-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4de81-104">方法</span><span class="sxs-lookup"><span data-stu-id="4de81-104">Methods</span></span>  
  
|<span data-ttu-id="4de81-105">方法</span><span class="sxs-lookup"><span data-stu-id="4de81-105">Method</span></span>|<span data-ttu-id="4de81-106">描述</span><span class="sxs-lookup"><span data-stu-id="4de81-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4de81-107">GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="4de81-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="4de81-108">获取静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="4de81-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="4de81-109">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="4de81-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="4de81-110">获取静态字段的名称。</span><span class="sxs-lookup"><span data-stu-id="4de81-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="4de81-111">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="4de81-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="4de81-112">获取静态字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="4de81-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4de81-113">备注</span><span class="sxs-lookup"><span data-stu-id="4de81-113">Remarks</span></span>  
 <span data-ttu-id="4de81-114">`ICorDebugStaticFieldSymbol` 接口用于检索某个静态字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="4de81-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4de81-115">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="4de81-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4de81-116">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="4de81-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4de81-117">要求</span><span class="sxs-lookup"><span data-stu-id="4de81-117">Requirements</span></span>  
 <span data-ttu-id="4de81-118">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4de81-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4de81-119">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="4de81-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4de81-120">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4de81-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4de81-121">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4de81-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de81-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="4de81-122">See also</span></span>

- [<span data-ttu-id="4de81-123">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="4de81-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="4de81-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="4de81-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4de81-125">调试</span><span class="sxs-lookup"><span data-stu-id="4de81-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
