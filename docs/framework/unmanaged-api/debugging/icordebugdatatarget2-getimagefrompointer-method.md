---
title: "ICorDebugDataTarget2::GetImageFromPointer 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cfe25a90fb2084c1f58eff5b42e24b15decb0163
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="9102b-102">ICorDebugDataTarget2::GetImageFromPointer 方法</span><span class="sxs-lookup"><span data-stu-id="9102b-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="9102b-103">返回该模块地址中的模块基址和大小。</span><span class="sxs-lookup"><span data-stu-id="9102b-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9102b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9102b-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9102b-105">参数</span><span class="sxs-lookup"><span data-stu-id="9102b-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="9102b-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值表示模块中的地址。</span><span class="sxs-lookup"><span data-stu-id="9102b-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="9102b-107">[out]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)表示模块的基址的值。</span><span class="sxs-lookup"><span data-stu-id="9102b-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="9102b-108">指针指向模块大小。</span><span class="sxs-lookup"><span data-stu-id="9102b-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9102b-109">备注</span><span class="sxs-lookup"><span data-stu-id="9102b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9102b-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="9102b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9102b-111">惠?</span><span class="sxs-lookup"><span data-stu-id="9102b-111">Requirements</span></span>  
 <span data-ttu-id="9102b-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9102b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9102b-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9102b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9102b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9102b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9102b-115">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9102b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9102b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9102b-116">See Also</span></span>  
 [<span data-ttu-id="9102b-117">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="9102b-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="9102b-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="9102b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
