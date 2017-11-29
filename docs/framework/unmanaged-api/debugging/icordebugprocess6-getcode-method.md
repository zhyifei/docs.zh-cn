---
title: "ICorDebugProcess6::GetCode 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c69ce290a486960978ddaf87203328df4f392b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="e744d-102">ICorDebugProcess6::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="e744d-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="e744d-103">获取特定代码地址上的托管代码的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e744d-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e744d-104">语法</span><span class="sxs-lookup"><span data-stu-id="e744d-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e744d-105">参数</span><span class="sxs-lookup"><span data-stu-id="e744d-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="e744d-106">[in]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值指定的托管的代码段的起始地址。</span><span class="sxs-lookup"><span data-stu-id="e744d-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="e744d-107">[out]指向表示托管代码段"icor 调试代码"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e744d-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e744d-108">备注</span><span class="sxs-lookup"><span data-stu-id="e744d-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e744d-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="e744d-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e744d-110">要求</span><span class="sxs-lookup"><span data-stu-id="e744d-110">Requirements</span></span>  
 <span data-ttu-id="e744d-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e744d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e744d-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e744d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e744d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e744d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e744d-114">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e744d-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e744d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e744d-115">See Also</span></span>  
 [<span data-ttu-id="e744d-116">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="e744d-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="e744d-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="e744d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
