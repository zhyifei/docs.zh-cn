---
title: "ICorDebugMemoryBuffer 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80002d064c48a90236a64a3d0a56fab5877cf411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="e74b8-102">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="e74b8-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="e74b8-103">表示内存中缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e74b8-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e74b8-104">方法</span><span class="sxs-lookup"><span data-stu-id="e74b8-104">Methods</span></span>  
  
|<span data-ttu-id="e74b8-105">方法</span><span class="sxs-lookup"><span data-stu-id="e74b8-105">Method</span></span>|<span data-ttu-id="e74b8-106">描述</span><span class="sxs-lookup"><span data-stu-id="e74b8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e74b8-107">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="e74b8-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="e74b8-108">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e74b8-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="e74b8-109">GetStartAddress 方法</span><span class="sxs-lookup"><span data-stu-id="e74b8-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="e74b8-110">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="e74b8-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e74b8-111">备注</span><span class="sxs-lookup"><span data-stu-id="e74b8-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e74b8-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="e74b8-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e74b8-113">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="e74b8-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e74b8-114">要求</span><span class="sxs-lookup"><span data-stu-id="e74b8-114">Requirements</span></span>  
 <span data-ttu-id="e74b8-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e74b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e74b8-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e74b8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e74b8-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e74b8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e74b8-118">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e74b8-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e74b8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e74b8-119">See Also</span></span>  
 [<span data-ttu-id="e74b8-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="e74b8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e74b8-121">调试</span><span class="sxs-lookup"><span data-stu-id="e74b8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
