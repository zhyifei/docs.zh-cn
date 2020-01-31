---
title: ICorDebugMemoryBuffer 接口
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: fa1bbca1e771cbc2b3475891862875b97b9e7f90
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793139"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="3dba2-102">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="3dba2-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="3dba2-103">表示内存中缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3dba2-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3dba2-104">方法</span><span class="sxs-lookup"><span data-stu-id="3dba2-104">Methods</span></span>  
  
|<span data-ttu-id="3dba2-105">方法</span><span class="sxs-lookup"><span data-stu-id="3dba2-105">Method</span></span>|<span data-ttu-id="3dba2-106">描述</span><span class="sxs-lookup"><span data-stu-id="3dba2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3dba2-107">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="3dba2-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="3dba2-108">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="3dba2-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="3dba2-109">GetStartAddress 方法</span><span class="sxs-lookup"><span data-stu-id="3dba2-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="3dba2-110">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="3dba2-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dba2-111">备注</span><span class="sxs-lookup"><span data-stu-id="3dba2-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dba2-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="3dba2-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="3dba2-113">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="3dba2-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dba2-114">需求</span><span class="sxs-lookup"><span data-stu-id="3dba2-114">Requirements</span></span>  
 <span data-ttu-id="3dba2-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3dba2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dba2-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dba2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dba2-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dba2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dba2-118">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dba2-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dba2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dba2-119">See also</span></span>

- [<span data-ttu-id="3dba2-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="3dba2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3dba2-121">调试</span><span class="sxs-lookup"><span data-stu-id="3dba2-121">Debugging</span></span>](index.md)
