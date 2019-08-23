---
title: ICorDebugMemoryBuffer::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c88d389f80b4b3d811d95f65acd41f294d076b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969081"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="113d0-102">ICorDebugMemoryBuffer::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="113d0-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="113d0-103">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="113d0-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="113d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="113d0-105">参数</span><span class="sxs-lookup"><span data-stu-id="113d0-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="113d0-106">[out] 指向内存缓冲区大小的指针。</span><span class="sxs-lookup"><span data-stu-id="113d0-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="113d0-107">备注</span><span class="sxs-lookup"><span data-stu-id="113d0-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="113d0-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="113d0-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="113d0-109">要求</span><span class="sxs-lookup"><span data-stu-id="113d0-109">Requirements</span></span>  
 <span data-ttu-id="113d0-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="113d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="113d0-111">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="113d0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="113d0-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="113d0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="113d0-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="113d0-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113d0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="113d0-114">See also</span></span>

- [<span data-ttu-id="113d0-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="113d0-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="113d0-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="113d0-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
