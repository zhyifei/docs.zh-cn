---
title: "ICorDebugILCode 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 51c4de0c-3813-4142-be25-a85bb84efb90
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b9629129b1ab24a2ba5708e808140078baa81ff3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilcode-interface"></a><span data-ttu-id="a7338-102">ICorDebugILCode 接口</span><span class="sxs-lookup"><span data-stu-id="a7338-102">ICorDebugILCode Interface</span></span>
<span data-ttu-id="a7338-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="a7338-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a7338-104">表示中间语言 (IL) 代码段。</span><span class="sxs-lookup"><span data-stu-id="a7338-104">Represents a segment of intermediate language (IL) code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7338-105">方法</span><span class="sxs-lookup"><span data-stu-id="a7338-105">Methods</span></span>  
  
|<span data-ttu-id="a7338-106">方法</span><span class="sxs-lookup"><span data-stu-id="a7338-106">Method</span></span>|<span data-ttu-id="a7338-107">描述</span><span class="sxs-lookup"><span data-stu-id="a7338-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7338-108">GetEHClauses 方法</span><span class="sxs-lookup"><span data-stu-id="a7338-108">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)|<span data-ttu-id="a7338-109">返回指向为此 IL 定义的异常处理 (EH) 子句列表的指针。</span><span class="sxs-lookup"><span data-stu-id="a7338-109">Returns a pointer to a list of exception handling (EH) clauses that are defined for this IL.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7338-110">惠?</span><span class="sxs-lookup"><span data-stu-id="a7338-110">Requirements</span></span>  
 <span data-ttu-id="a7338-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7338-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7338-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7338-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7338-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7338-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7338-114">**.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7338-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7338-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7338-115">See Also</span></span>  
 [<span data-ttu-id="a7338-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="a7338-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a7338-117">调试</span><span class="sxs-lookup"><span data-stu-id="a7338-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
