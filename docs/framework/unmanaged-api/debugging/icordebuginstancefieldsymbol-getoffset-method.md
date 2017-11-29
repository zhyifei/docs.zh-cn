---
title: "ICorDebugInstanceFieldSymbol::GetName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 534e3238a4b20e390c4f2168629e0ba93620f55a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="01ffa-102">ICorDebugInstanceFieldSymbol::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="01ffa-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="01ffa-103">获取父类中此示例字段的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="01ffa-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01ffa-104">语法</span><span class="sxs-lookup"><span data-stu-id="01ffa-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01ffa-105">参数</span><span class="sxs-lookup"><span data-stu-id="01ffa-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="01ffa-106">指向此示例字段在父类中偏移的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="01ffa-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01ffa-107">备注</span><span class="sxs-lookup"><span data-stu-id="01ffa-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01ffa-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="01ffa-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01ffa-109">要求</span><span class="sxs-lookup"><span data-stu-id="01ffa-109">Requirements</span></span>  
 <span data-ttu-id="01ffa-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01ffa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01ffa-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01ffa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01ffa-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01ffa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01ffa-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01ffa-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ffa-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01ffa-114">See Also</span></span>  
 [<span data-ttu-id="01ffa-115">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="01ffa-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="01ffa-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="01ffa-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
