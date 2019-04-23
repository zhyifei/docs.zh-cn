---
title: ICorDebugMemoryBuffer::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d687f2bbd3c20564368d4246961b56382ea14cf5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099672"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="ae8a5-102">ICorDebugMemoryBuffer::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="ae8a5-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="ae8a5-103">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ae8a5-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae8a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae8a5-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae8a5-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae8a5-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="ae8a5-106">[out] 指向内存缓冲区大小的指针。</span><span class="sxs-lookup"><span data-stu-id="ae8a5-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae8a5-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae8a5-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae8a5-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ae8a5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae8a5-109">要求</span><span class="sxs-lookup"><span data-stu-id="ae8a5-109">Requirements</span></span>  
 <span data-ttu-id="ae8a5-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae8a5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae8a5-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae8a5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae8a5-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae8a5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae8a5-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae8a5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8a5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae8a5-114">See also</span></span>

- [<span data-ttu-id="ae8a5-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="ae8a5-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="ae8a5-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="ae8a5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
