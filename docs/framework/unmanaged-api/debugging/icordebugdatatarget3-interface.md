---
title: ICorDebugDataTarget3 接口
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee94e25201dee4999fd5acb2be44a80454e9efbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911416"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="ef713-102">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="ef713-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="ef713-103">对[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口进行逻辑扩展, 以提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="ef713-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="ef713-104">方法</span><span class="sxs-lookup"><span data-stu-id="ef713-104">Method</span></span>  
  
|<span data-ttu-id="ef713-105">方法</span><span class="sxs-lookup"><span data-stu-id="ef713-105">Method</span></span>|<span data-ttu-id="ef713-106">描述</span><span class="sxs-lookup"><span data-stu-id="ef713-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef713-107">GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="ef713-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="ef713-108">获取到目前为止已加载的模块的列表。</span><span class="sxs-lookup"><span data-stu-id="ef713-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef713-109">备注</span><span class="sxs-lookup"><span data-stu-id="ef713-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef713-110">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ef713-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ef713-111">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="ef713-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef713-112">要求</span><span class="sxs-lookup"><span data-stu-id="ef713-112">Requirements</span></span>  
 <span data-ttu-id="ef713-113">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef713-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef713-114">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="ef713-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef713-115">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef713-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef713-116">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef713-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef713-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef713-117">See also</span></span>

- [<span data-ttu-id="ef713-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="ef713-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ef713-119">调试</span><span class="sxs-lookup"><span data-stu-id="ef713-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
