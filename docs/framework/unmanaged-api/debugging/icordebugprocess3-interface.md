---
title: ICorDebugProcess3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05900f55885f8f3a4c470d6842c42d0fc3e0171e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957447"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="0ebaa-102">ICorDebugProcess3 接口</span><span class="sxs-lookup"><span data-stu-id="0ebaa-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="0ebaa-103">控制自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="0ebaa-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ebaa-104">方法</span><span class="sxs-lookup"><span data-stu-id="0ebaa-104">Methods</span></span>  
  
|<span data-ttu-id="0ebaa-105">方法</span><span class="sxs-lookup"><span data-stu-id="0ebaa-105">Method</span></span>|<span data-ttu-id="0ebaa-106">描述</span><span class="sxs-lookup"><span data-stu-id="0ebaa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ebaa-107">SetEnableCustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="0ebaa-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="0ebaa-108">启用和禁用指定类型的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="0ebaa-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ebaa-109">备注</span><span class="sxs-lookup"><span data-stu-id="0ebaa-109">Remarks</span></span>  
 <span data-ttu-id="0ebaa-110">此接口以逻辑方式扩展 ICorDebugProcess 和 ICorDebugProcess2 接口。</span><span class="sxs-lookup"><span data-stu-id="0ebaa-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ebaa-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="0ebaa-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ebaa-112">要求</span><span class="sxs-lookup"><span data-stu-id="0ebaa-112">Requirements</span></span>  
 <span data-ttu-id="0ebaa-113">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ebaa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ebaa-114">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="0ebaa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ebaa-115">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ebaa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ebaa-116">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ebaa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebaa-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ebaa-117">See also</span></span>

- [<span data-ttu-id="0ebaa-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="0ebaa-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0ebaa-119">调试</span><span class="sxs-lookup"><span data-stu-id="0ebaa-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
