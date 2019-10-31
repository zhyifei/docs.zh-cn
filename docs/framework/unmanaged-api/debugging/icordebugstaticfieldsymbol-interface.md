---
title: ICorDebugStaticFieldSymbol 接口
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: 0891df1fc0528ff485605b2c4168fcff0adff990
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131709"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="bbea1-102">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="bbea1-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="bbea1-103">表示某个静态字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="bbea1-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bbea1-104">方法</span><span class="sxs-lookup"><span data-stu-id="bbea1-104">Methods</span></span>  
  
|<span data-ttu-id="bbea1-105">方法</span><span class="sxs-lookup"><span data-stu-id="bbea1-105">Method</span></span>|<span data-ttu-id="bbea1-106">描述</span><span class="sxs-lookup"><span data-stu-id="bbea1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bbea1-107">GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="bbea1-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="bbea1-108">获取静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="bbea1-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="bbea1-109">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="bbea1-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="bbea1-110">获取静态字段的名称。</span><span class="sxs-lookup"><span data-stu-id="bbea1-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="bbea1-111">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="bbea1-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="bbea1-112">获取静态字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="bbea1-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbea1-113">备注</span><span class="sxs-lookup"><span data-stu-id="bbea1-113">Remarks</span></span>  
 <span data-ttu-id="bbea1-114">`ICorDebugStaticFieldSymbol` 接口用于检索某个静态字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="bbea1-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bbea1-115">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="bbea1-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="bbea1-116">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="bbea1-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbea1-117">要求</span><span class="sxs-lookup"><span data-stu-id="bbea1-117">Requirements</span></span>  
 <span data-ttu-id="bbea1-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbea1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbea1-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbea1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbea1-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbea1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbea1-121">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbea1-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbea1-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbea1-122">See also</span></span>

- [<span data-ttu-id="bbea1-123">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="bbea1-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="bbea1-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="bbea1-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bbea1-125">调试</span><span class="sxs-lookup"><span data-stu-id="bbea1-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
