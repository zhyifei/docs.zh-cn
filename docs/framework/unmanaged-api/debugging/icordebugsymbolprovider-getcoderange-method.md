---
title: ICorDebugSymbolProvider::GetCodeRange 方法
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 392f526df53474dd2926e631e24ec5449bd1b199
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498466"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="df5c0-102">ICorDebugSymbolProvider::GetCodeRange 方法</span><span class="sxs-lookup"><span data-stu-id="df5c0-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="df5c0-103">给定方法的相对虚拟地址 (RVA)，获取该方法的起始地址和大小。</span><span class="sxs-lookup"><span data-stu-id="df5c0-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df5c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="df5c0-104">Syntax</span></span>  
  
```  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df5c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="df5c0-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="df5c0-106">[in] 方法中的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="df5c0-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="df5c0-107">[out] 指向该方法的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="df5c0-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="df5c0-108">指向方法代码大小（该方法的代码的字节数）的指针。</span><span class="sxs-lookup"><span data-stu-id="df5c0-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df5c0-109">备注</span><span class="sxs-lookup"><span data-stu-id="df5c0-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df5c0-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="df5c0-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df5c0-111">要求</span><span class="sxs-lookup"><span data-stu-id="df5c0-111">Requirements</span></span>  
 <span data-ttu-id="df5c0-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df5c0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df5c0-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df5c0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df5c0-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df5c0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df5c0-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df5c0-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df5c0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="df5c0-116">See also</span></span>
- [<span data-ttu-id="df5c0-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="df5c0-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="df5c0-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="df5c0-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
