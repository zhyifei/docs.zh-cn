---
title: "ICorDebugDataTarget3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c65bbfa033a3a585cdcfdb42cdda95f1de4aa412
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="319a7-102">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="319a7-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="319a7-103">合理扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口以提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="319a7-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="319a7-104">方法</span><span class="sxs-lookup"><span data-stu-id="319a7-104">Method</span></span>  
  
|<span data-ttu-id="319a7-105">方法</span><span class="sxs-lookup"><span data-stu-id="319a7-105">Method</span></span>|<span data-ttu-id="319a7-106">描述</span><span class="sxs-lookup"><span data-stu-id="319a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="319a7-107">GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="319a7-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="319a7-108">获取到目前为止已加载的模块的列表。</span><span class="sxs-lookup"><span data-stu-id="319a7-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="319a7-109">备注</span><span class="sxs-lookup"><span data-stu-id="319a7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="319a7-110">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="319a7-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="319a7-111">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="319a7-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="319a7-112">惠?</span><span class="sxs-lookup"><span data-stu-id="319a7-112">Requirements</span></span>  
 <span data-ttu-id="319a7-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="319a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="319a7-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="319a7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="319a7-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="319a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="319a7-116">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="319a7-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="319a7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="319a7-117">See Also</span></span>  
 [<span data-ttu-id="319a7-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="319a7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="319a7-119">调试</span><span class="sxs-lookup"><span data-stu-id="319a7-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
