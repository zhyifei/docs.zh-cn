---
title: ICorDebugProcess8 接口
ms.date: 03/30/2017
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbedff96abe525a1fe39d7255379c0e1612d5893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422254"
---
# <a name="icordebugprocess8-interface"></a><span data-ttu-id="0f260-102">ICorDebugProcess8 接口</span><span class="sxs-lookup"><span data-stu-id="0f260-102">ICorDebugProcess8 Interface</span></span>
<span data-ttu-id="0f260-103">[支持版本：[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 及更高版本]</span><span class="sxs-lookup"><span data-stu-id="0f260-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="0f260-104">合理扩展 ICorDebugProcess 接口以启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="0f260-104">Logically extends the ICorDebugProcess interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f260-105">方法</span><span class="sxs-lookup"><span data-stu-id="0f260-105">Methods</span></span>  
  
|<span data-ttu-id="0f260-106">方法</span><span class="sxs-lookup"><span data-stu-id="0f260-106">Method</span></span>|<span data-ttu-id="0f260-107">描述</span><span class="sxs-lookup"><span data-stu-id="0f260-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f260-108">EnableExceptionCallbacksOutsideOfMyCode 方法</span><span class="sxs-lookup"><span data-stu-id="0f260-108">EnableExceptionCallbacksOutsideOfMyCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|<span data-ttu-id="0f260-109">启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="0f260-109">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f260-110">备注</span><span class="sxs-lookup"><span data-stu-id="0f260-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f260-111">要求</span><span class="sxs-lookup"><span data-stu-id="0f260-111">Requirements</span></span>  
 <span data-ttu-id="0f260-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f260-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f260-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f260-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f260-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f260-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f260-115">**.NET framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f260-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f260-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f260-116">See Also</span></span>  
 [<span data-ttu-id="0f260-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="0f260-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0f260-118">调试</span><span class="sxs-lookup"><span data-stu-id="0f260-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
