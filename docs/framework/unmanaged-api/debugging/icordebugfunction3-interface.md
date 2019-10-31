---
title: ICorDebugFunction3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: fc50fd7180aaf5c1cff2147268d34921eec39e8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137767"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="0e367-102">ICorDebugFunction3 接口</span><span class="sxs-lookup"><span data-stu-id="0e367-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="0e367-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="0e367-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0e367-104">对 ICorDebugFunction 接口进行逻辑扩展，以提供对 ReJIT 请求中的代码的访问。</span><span class="sxs-lookup"><span data-stu-id="0e367-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e367-105">方法</span><span class="sxs-lookup"><span data-stu-id="0e367-105">Methods</span></span>  
  
|<span data-ttu-id="0e367-106">方法</span><span class="sxs-lookup"><span data-stu-id="0e367-106">Method</span></span>|<span data-ttu-id="0e367-107">描述</span><span class="sxs-lookup"><span data-stu-id="0e367-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e367-108">GetActiveReJitRequestILCode 方法</span><span class="sxs-lookup"><span data-stu-id="0e367-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="0e367-109">获取一个接口指针，该指针指向包含活动 ReJIT 请求中的 IL 的[ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="0e367-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e367-110">备注</span><span class="sxs-lookup"><span data-stu-id="0e367-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e367-111">要求</span><span class="sxs-lookup"><span data-stu-id="0e367-111">Requirements</span></span>  
 <span data-ttu-id="0e367-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e367-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e367-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e367-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e367-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e367-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e367-115">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e367-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e367-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e367-116">See also</span></span>

- [<span data-ttu-id="0e367-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="0e367-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0e367-118">调试</span><span class="sxs-lookup"><span data-stu-id="0e367-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="0e367-119">ReJIT：操作方法指南</span><span class="sxs-lookup"><span data-stu-id="0e367-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
