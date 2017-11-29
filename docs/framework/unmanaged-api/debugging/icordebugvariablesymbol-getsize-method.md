---
title: "ICorDebugVariableSymbol::GetSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ea4a77b08b12c3f067d51f9dfe2c961192c3354
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="6bda1-102">ICorDebugVariableSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="6bda1-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="6bda1-103">获取变量的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6bda1-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bda1-104">语法</span><span class="sxs-lookup"><span data-stu-id="6bda1-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bda1-105">参数</span><span class="sxs-lookup"><span data-stu-id="6bda1-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="6bda1-106">指向包含变量大小的 32 位无符号整数的指针。</span><span class="sxs-lookup"><span data-stu-id="6bda1-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bda1-107">备注</span><span class="sxs-lookup"><span data-stu-id="6bda1-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bda1-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="6bda1-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bda1-109">要求</span><span class="sxs-lookup"><span data-stu-id="6bda1-109">Requirements</span></span>  
 <span data-ttu-id="6bda1-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6bda1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bda1-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bda1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bda1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bda1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bda1-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bda1-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bda1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bda1-114">See Also</span></span>  
 [<span data-ttu-id="6bda1-115">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="6bda1-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="6bda1-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="6bda1-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
