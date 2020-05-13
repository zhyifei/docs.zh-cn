---
title: ICorDebugMemoryBuffer::GetStartAddress 方法
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 47369c744ee42fb03857a3e69063a04e4f509d0d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212342"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="83c78-102">ICorDebugMemoryBuffer::GetStartAddress 方法</span><span class="sxs-lookup"><span data-stu-id="83c78-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="83c78-103">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="83c78-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c78-104">语法</span><span class="sxs-lookup"><span data-stu-id="83c78-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c78-105">参数</span><span class="sxs-lookup"><span data-stu-id="83c78-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="83c78-106">[out] 指向内存缓冲区起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="83c78-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83c78-107">备注</span><span class="sxs-lookup"><span data-stu-id="83c78-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="83c78-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="83c78-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c78-109">要求</span><span class="sxs-lookup"><span data-stu-id="83c78-109">Requirements</span></span>  
 <span data-ttu-id="83c78-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83c78-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c78-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83c78-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83c78-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83c78-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83c78-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c78-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c78-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="83c78-114">See also</span></span>

- [<span data-ttu-id="83c78-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="83c78-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="83c78-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="83c78-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
