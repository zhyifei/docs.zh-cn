---
title: ICorDebugMemoryBuffer::GetStartAddress 方法
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aa816ea9e6185791e09bcdb0e47c50761a5ebc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422928"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="67dab-102">ICorDebugMemoryBuffer::GetStartAddress 方法</span><span class="sxs-lookup"><span data-stu-id="67dab-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="67dab-103">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="67dab-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67dab-104">语法</span><span class="sxs-lookup"><span data-stu-id="67dab-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67dab-105">参数</span><span class="sxs-lookup"><span data-stu-id="67dab-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="67dab-106">[out] 指向内存缓冲区起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="67dab-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67dab-107">备注</span><span class="sxs-lookup"><span data-stu-id="67dab-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="67dab-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="67dab-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67dab-109">要求</span><span class="sxs-lookup"><span data-stu-id="67dab-109">Requirements</span></span>  
 <span data-ttu-id="67dab-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67dab-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67dab-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67dab-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67dab-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67dab-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67dab-113">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67dab-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67dab-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="67dab-114">See Also</span></span>  
 [<span data-ttu-id="67dab-115">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="67dab-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="67dab-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="67dab-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
