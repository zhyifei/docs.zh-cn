---
title: 'Icordebugmemorybuffer:: Getstartaddress 方法'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58649a0fc12ce63a1307af5d831dbf5e0d5a776a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136976"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="c442f-102">Icordebugmemorybuffer:: Getstartaddress 方法</span><span class="sxs-lookup"><span data-stu-id="c442f-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="c442f-103">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="c442f-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c442f-104">语法</span><span class="sxs-lookup"><span data-stu-id="c442f-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c442f-105">参数</span><span class="sxs-lookup"><span data-stu-id="c442f-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c442f-106">[out] 指向内存缓冲区起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c442f-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c442f-107">备注</span><span class="sxs-lookup"><span data-stu-id="c442f-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c442f-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="c442f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c442f-109">要求</span><span class="sxs-lookup"><span data-stu-id="c442f-109">Requirements</span></span>  
 <span data-ttu-id="c442f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c442f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c442f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c442f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c442f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c442f-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c442f-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c442f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c442f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c442f-114">See also</span></span>

- [<span data-ttu-id="c442f-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="c442f-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="c442f-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="c442f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
