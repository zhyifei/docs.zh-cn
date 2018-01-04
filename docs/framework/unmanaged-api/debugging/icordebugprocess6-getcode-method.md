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
ms.workload: dotnet
ms.openlocfilehash: f532c52ac487915b76d624e62886a93db6d1eae4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="00a30-102">ICorDebugProcess6::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="00a30-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="00a30-103">获取特定代码地址上的托管代码的相关信息。</span><span class="sxs-lookup"><span data-stu-id="00a30-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a30-104">语法</span><span class="sxs-lookup"><span data-stu-id="00a30-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00a30-105">参数</span><span class="sxs-lookup"><span data-stu-id="00a30-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="00a30-106">[in]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值指定的托管的代码段的起始地址。</span><span class="sxs-lookup"><span data-stu-id="00a30-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="00a30-107">[out]指向表示托管代码段"icor 调试代码"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="00a30-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00a30-108">备注</span><span class="sxs-lookup"><span data-stu-id="00a30-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00a30-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="00a30-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a30-110">惠?</span><span class="sxs-lookup"><span data-stu-id="00a30-110">Requirements</span></span>  
 <span data-ttu-id="00a30-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00a30-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a30-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00a30-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00a30-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00a30-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00a30-114">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a30-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a30-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="00a30-115">See Also</span></span>  
 [<span data-ttu-id="00a30-116">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="00a30-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="00a30-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="00a30-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
