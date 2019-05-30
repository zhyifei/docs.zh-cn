---
title: ICorDebugProcess8 接口
ms.date: 03/30/2017
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6db1bc7e87750a36415439707777fed99e358ea
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300534"
---
# <a name="icordebugprocess8-interface"></a><span data-ttu-id="732bd-102">ICorDebugProcess8 接口</span><span class="sxs-lookup"><span data-stu-id="732bd-102">ICorDebugProcess8 Interface</span></span>
<span data-ttu-id="732bd-103">[.NET Framework 4.6 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="732bd-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="732bd-104">合理扩展 ICorDebugProcess 接口来启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="732bd-104">Logically extends the ICorDebugProcess interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="732bd-105">方法</span><span class="sxs-lookup"><span data-stu-id="732bd-105">Methods</span></span>  
  
|<span data-ttu-id="732bd-106">方法</span><span class="sxs-lookup"><span data-stu-id="732bd-106">Method</span></span>|<span data-ttu-id="732bd-107">描述</span><span class="sxs-lookup"><span data-stu-id="732bd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="732bd-108">EnableExceptionCallbacksOutsideOfMyCode 方法</span><span class="sxs-lookup"><span data-stu-id="732bd-108">EnableExceptionCallbacksOutsideOfMyCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|<span data-ttu-id="732bd-109">启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="732bd-109">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="732bd-110">备注</span><span class="sxs-lookup"><span data-stu-id="732bd-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="732bd-111">要求</span><span class="sxs-lookup"><span data-stu-id="732bd-111">Requirements</span></span>  
 <span data-ttu-id="732bd-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="732bd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="732bd-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="732bd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="732bd-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="732bd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="732bd-115">**.NET Framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="732bd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732bd-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="732bd-116">See also</span></span>

- [<span data-ttu-id="732bd-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="732bd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="732bd-118">调试</span><span class="sxs-lookup"><span data-stu-id="732bd-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
