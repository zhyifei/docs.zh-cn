---
title: "ICorDebugFunction3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction3
api_location: mscordbi.dll
api_type: COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfe0c420c1c9b8074b7cb769e592f8cb2f5916e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="016ab-102">ICorDebugFunction3 接口</span><span class="sxs-lookup"><span data-stu-id="016ab-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="016ab-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="016ab-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="016ab-104">合理扩展 ICorDebugFunction 接口以提供对代码的访问，ReJIT 请求中。</span><span class="sxs-lookup"><span data-stu-id="016ab-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="016ab-105">方法</span><span class="sxs-lookup"><span data-stu-id="016ab-105">Methods</span></span>  
  
|<span data-ttu-id="016ab-106">方法</span><span class="sxs-lookup"><span data-stu-id="016ab-106">Method</span></span>|<span data-ttu-id="016ab-107">描述</span><span class="sxs-lookup"><span data-stu-id="016ab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="016ab-108">GetActiveReJitRequestILCode 方法</span><span class="sxs-lookup"><span data-stu-id="016ab-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="016ab-109">获取到的接口指针[ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)包含活动 ReJIT 请求中的 IL。</span><span class="sxs-lookup"><span data-stu-id="016ab-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="016ab-110">备注</span><span class="sxs-lookup"><span data-stu-id="016ab-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="016ab-111">要求</span><span class="sxs-lookup"><span data-stu-id="016ab-111">Requirements</span></span>  
 <span data-ttu-id="016ab-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="016ab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="016ab-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="016ab-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="016ab-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="016ab-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="016ab-115">**.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="016ab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016ab-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="016ab-116">See Also</span></span>  
 [<span data-ttu-id="016ab-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="016ab-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="016ab-118">调试</span><span class="sxs-lookup"><span data-stu-id="016ab-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="016ab-119">ReJIT: 操作方法指南</span><span class="sxs-lookup"><span data-stu-id="016ab-119">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
