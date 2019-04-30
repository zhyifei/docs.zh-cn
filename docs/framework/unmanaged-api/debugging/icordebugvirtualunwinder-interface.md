---
title: ICorDebugVirtualUnwinder 接口
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639cfc514d2a206f0de72db4b0bac02b53305ae3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946154"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="0d144-102">ICorDebugVirtualUnwinder 接口</span><span class="sxs-lookup"><span data-stu-id="0d144-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="0d144-103">提供帮助堆栈展开的方法。</span><span class="sxs-lookup"><span data-stu-id="0d144-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d144-104">方法</span><span class="sxs-lookup"><span data-stu-id="0d144-104">Methods</span></span>  
  
|<span data-ttu-id="0d144-105">方法</span><span class="sxs-lookup"><span data-stu-id="0d144-105">Method</span></span>|<span data-ttu-id="0d144-106">名称</span><span class="sxs-lookup"><span data-stu-id="0d144-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="0d144-107">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="0d144-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="0d144-108">获取此展开器的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="0d144-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="0d144-109">Next 方法</span><span class="sxs-lookup"><span data-stu-id="0d144-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="0d144-110">前进到调用方的上下文。</span><span class="sxs-lookup"><span data-stu-id="0d144-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d144-111">备注</span><span class="sxs-lookup"><span data-stu-id="0d144-111">Remarks</span></span>  
 <span data-ttu-id="0d144-112">`ICorDebugVirtualUnwinder` 接口的成员由调试器来实现，从而在堆栈展开中提供帮助。</span><span class="sxs-lookup"><span data-stu-id="0d144-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d144-113">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="0d144-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0d144-114">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="0d144-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d144-115">要求</span><span class="sxs-lookup"><span data-stu-id="0d144-115">Requirements</span></span>  
 <span data-ttu-id="0d144-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d144-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d144-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d144-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d144-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d144-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d144-119">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d144-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d144-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d144-120">See also</span></span>

- [<span data-ttu-id="0d144-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="0d144-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0d144-122">调试</span><span class="sxs-lookup"><span data-stu-id="0d144-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
