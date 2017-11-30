---
title: "ICorDebugStaticFieldSymbol::GetAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 20c0c934772625d27057957d00e53fb4b485c4fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="8e74e-102">ICorDebugStaticFieldSymbol::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="8e74e-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="8e74e-103">获取静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="8e74e-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e74e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e74e-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e74e-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e74e-105">Parameters</span></span>  
 <span data-ttu-id="8e74e-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="8e74e-106">pRVA</span></span>  
 <span data-ttu-id="8e74e-107">[out] 指向静态字段的相对虚拟地址 (RVA) 的指针。</span><span class="sxs-lookup"><span data-stu-id="8e74e-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e74e-108">备注</span><span class="sxs-lookup"><span data-stu-id="8e74e-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e74e-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="8e74e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e74e-110">要求</span><span class="sxs-lookup"><span data-stu-id="8e74e-110">Requirements</span></span>  
 <span data-ttu-id="8e74e-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e74e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e74e-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e74e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e74e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e74e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e74e-114">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e74e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e74e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e74e-115">See Also</span></span>  
 [<span data-ttu-id="8e74e-116">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="8e74e-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="8e74e-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="8e74e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
