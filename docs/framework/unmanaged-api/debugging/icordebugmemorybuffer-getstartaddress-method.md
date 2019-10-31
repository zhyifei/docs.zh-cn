---
title: ICorDebugMemoryBuffer：： GetStartAddress 方法
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: e2876398ceaf863bbb3c7e576d59b89c52f1bdaf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127992"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="b8fbd-102">ICorDebugMemoryBuffer：： GetStartAddress 方法</span><span class="sxs-lookup"><span data-stu-id="b8fbd-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="b8fbd-103">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="b8fbd-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8fbd-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8fbd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8fbd-105">参数</span><span class="sxs-lookup"><span data-stu-id="b8fbd-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b8fbd-106">[out] 指向内存缓冲区起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b8fbd-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8fbd-107">备注</span><span class="sxs-lookup"><span data-stu-id="b8fbd-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="b8fbd-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b8fbd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8fbd-109">要求</span><span class="sxs-lookup"><span data-stu-id="b8fbd-109">Requirements</span></span>  
 <span data-ttu-id="b8fbd-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fbd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8fbd-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8fbd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8fbd-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8fbd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8fbd-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8fbd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8fbd-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8fbd-114">See also</span></span>

- [<span data-ttu-id="b8fbd-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="b8fbd-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="b8fbd-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="b8fbd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
