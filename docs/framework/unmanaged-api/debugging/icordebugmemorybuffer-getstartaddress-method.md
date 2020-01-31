---
title: ICorDebugMemoryBuffer::GetStartAddress 方法
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f2b09c847a6bf577b78c8155f85f07b93877fbe9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793172"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="61b5b-102">ICorDebugMemoryBuffer::GetStartAddress 方法</span><span class="sxs-lookup"><span data-stu-id="61b5b-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="61b5b-103">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="61b5b-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61b5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="61b5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61b5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="61b5b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="61b5b-106">[out] 指向内存缓冲区起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="61b5b-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61b5b-107">备注</span><span class="sxs-lookup"><span data-stu-id="61b5b-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="61b5b-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="61b5b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61b5b-109">需求</span><span class="sxs-lookup"><span data-stu-id="61b5b-109">Requirements</span></span>  
 <span data-ttu-id="61b5b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61b5b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61b5b-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61b5b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61b5b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61b5b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61b5b-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61b5b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b5b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61b5b-114">See also</span></span>

- [<span data-ttu-id="61b5b-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="61b5b-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="61b5b-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="61b5b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
