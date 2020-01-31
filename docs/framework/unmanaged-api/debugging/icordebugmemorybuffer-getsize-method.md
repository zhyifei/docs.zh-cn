---
title: ICorDebugMemoryBuffer::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 51c13b67951c714d1aec602ffea22891328565a0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793175"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="43876-102">ICorDebugMemoryBuffer::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="43876-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="43876-103">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="43876-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43876-104">语法</span><span class="sxs-lookup"><span data-stu-id="43876-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43876-105">参数</span><span class="sxs-lookup"><span data-stu-id="43876-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="43876-106">[out] 指向内存缓冲区大小的指针。</span><span class="sxs-lookup"><span data-stu-id="43876-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43876-107">备注</span><span class="sxs-lookup"><span data-stu-id="43876-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43876-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="43876-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43876-109">需求</span><span class="sxs-lookup"><span data-stu-id="43876-109">Requirements</span></span>  
 <span data-ttu-id="43876-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43876-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43876-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43876-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43876-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43876-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43876-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43876-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43876-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43876-114">See also</span></span>

- [<span data-ttu-id="43876-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="43876-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="43876-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="43876-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
