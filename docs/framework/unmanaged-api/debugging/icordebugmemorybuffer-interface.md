---
title: ICorDebugMemoryBuffer 接口
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 9e43f9a2297eb56755c7a6bba73e994441cbfeaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127978"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="f6dcc-102">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="f6dcc-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="f6dcc-103">表示内存中缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f6dcc-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6dcc-104">方法</span><span class="sxs-lookup"><span data-stu-id="f6dcc-104">Methods</span></span>  
  
|<span data-ttu-id="f6dcc-105">方法</span><span class="sxs-lookup"><span data-stu-id="f6dcc-105">Method</span></span>|<span data-ttu-id="f6dcc-106">描述</span><span class="sxs-lookup"><span data-stu-id="f6dcc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6dcc-107">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="f6dcc-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="f6dcc-108">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f6dcc-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="f6dcc-109">GetStartAddress 方法</span><span class="sxs-lookup"><span data-stu-id="f6dcc-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="f6dcc-110">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="f6dcc-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6dcc-111">备注</span><span class="sxs-lookup"><span data-stu-id="f6dcc-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6dcc-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f6dcc-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f6dcc-113">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="f6dcc-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6dcc-114">要求</span><span class="sxs-lookup"><span data-stu-id="f6dcc-114">Requirements</span></span>  
 <span data-ttu-id="f6dcc-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6dcc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6dcc-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6dcc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6dcc-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6dcc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6dcc-118">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6dcc-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6dcc-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6dcc-119">See also</span></span>

- [<span data-ttu-id="f6dcc-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="f6dcc-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f6dcc-121">调试</span><span class="sxs-lookup"><span data-stu-id="f6dcc-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
