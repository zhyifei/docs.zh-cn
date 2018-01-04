---
title: "ICorDebugStaticFieldSymbol::GetSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b67cbe6858e91e089c36047d6ed83743e45e1d1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="953d8-102">ICorDebugStaticFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="953d8-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="953d8-103">获取静态字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="953d8-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="953d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="953d8-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="953d8-105">参数</span><span class="sxs-lookup"><span data-stu-id="953d8-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="953d8-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="953d8-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="953d8-107">备注</span><span class="sxs-lookup"><span data-stu-id="953d8-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="953d8-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="953d8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="953d8-109">惠?</span><span class="sxs-lookup"><span data-stu-id="953d8-109">Requirements</span></span>  
 <span data-ttu-id="953d8-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="953d8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="953d8-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="953d8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="953d8-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="953d8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="953d8-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="953d8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="953d8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="953d8-114">See Also</span></span>  
 [<span data-ttu-id="953d8-115">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="953d8-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="953d8-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="953d8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
