---
title: ICorDebugDataTarget3 接口
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3b0d67d390931cc92c0b6a1320f66545517cde3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223038"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="b242f-102">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="b242f-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="b242f-103">进行逻辑扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口以提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="b242f-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="b242f-104">方法</span><span class="sxs-lookup"><span data-stu-id="b242f-104">Method</span></span>  
  
|<span data-ttu-id="b242f-105">方法</span><span class="sxs-lookup"><span data-stu-id="b242f-105">Method</span></span>|<span data-ttu-id="b242f-106">描述</span><span class="sxs-lookup"><span data-stu-id="b242f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b242f-107">GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="b242f-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="b242f-108">获取到目前为止已加载的模块的列表。</span><span class="sxs-lookup"><span data-stu-id="b242f-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b242f-109">备注</span><span class="sxs-lookup"><span data-stu-id="b242f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b242f-110">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b242f-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b242f-111">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="b242f-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b242f-112">要求</span><span class="sxs-lookup"><span data-stu-id="b242f-112">Requirements</span></span>  
 <span data-ttu-id="b242f-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b242f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b242f-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b242f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b242f-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b242f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b242f-116">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b242f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b242f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b242f-117">See also</span></span>

- [<span data-ttu-id="b242f-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="b242f-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b242f-119">调试</span><span class="sxs-lookup"><span data-stu-id="b242f-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
