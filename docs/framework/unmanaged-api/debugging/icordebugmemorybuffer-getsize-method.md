---
title: ICorDebugMemoryBuffer::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caf95e0b5c8d4ae942bb428f53d4e58313e0e78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414747"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="16c9b-102">ICorDebugMemoryBuffer::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="16c9b-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="16c9b-103">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="16c9b-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c9b-104">语法</span><span class="sxs-lookup"><span data-stu-id="16c9b-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16c9b-105">参数</span><span class="sxs-lookup"><span data-stu-id="16c9b-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="16c9b-106">[out] 指向内存缓冲区大小的指针。</span><span class="sxs-lookup"><span data-stu-id="16c9b-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16c9b-107">备注</span><span class="sxs-lookup"><span data-stu-id="16c9b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16c9b-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="16c9b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c9b-109">要求</span><span class="sxs-lookup"><span data-stu-id="16c9b-109">Requirements</span></span>  
 <span data-ttu-id="16c9b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="16c9b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16c9b-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16c9b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16c9b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16c9b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16c9b-113">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16c9b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c9b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="16c9b-114">See Also</span></span>  
 [<span data-ttu-id="16c9b-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="16c9b-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="16c9b-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="16c9b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
