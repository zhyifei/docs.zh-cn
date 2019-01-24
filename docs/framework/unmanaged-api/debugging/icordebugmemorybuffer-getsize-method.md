---
title: ICorDebugMemoryBuffer::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5984addb41c33468068f7ad24a15533f75dc367
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714719"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="a4ade-102">ICorDebugMemoryBuffer::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="a4ade-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="a4ade-103">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a4ade-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ade-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4ade-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4ade-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4ade-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="a4ade-106">[out] 指向内存缓冲区大小的指针。</span><span class="sxs-lookup"><span data-stu-id="a4ade-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4ade-107">备注</span><span class="sxs-lookup"><span data-stu-id="a4ade-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4ade-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a4ade-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4ade-109">要求</span><span class="sxs-lookup"><span data-stu-id="a4ade-109">Requirements</span></span>  
 <span data-ttu-id="a4ade-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4ade-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4ade-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4ade-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4ade-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4ade-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4ade-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4ade-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ade-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4ade-114">See also</span></span>
- [<span data-ttu-id="a4ade-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="a4ade-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="a4ade-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="a4ade-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
