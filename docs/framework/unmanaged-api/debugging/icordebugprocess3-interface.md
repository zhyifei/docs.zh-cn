---
title: "ICorDebugProcess3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess3
helpviewer_keywords: ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8483c53ed8b35fd3948ec42b14859146afa8ce42
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="5e2b2-102">ICorDebugProcess3 接口</span><span class="sxs-lookup"><span data-stu-id="5e2b2-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="5e2b2-103">控制自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="5e2b2-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e2b2-104">方法</span><span class="sxs-lookup"><span data-stu-id="5e2b2-104">Methods</span></span>  
  
|<span data-ttu-id="5e2b2-105">方法</span><span class="sxs-lookup"><span data-stu-id="5e2b2-105">Method</span></span>|<span data-ttu-id="5e2b2-106">描述</span><span class="sxs-lookup"><span data-stu-id="5e2b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e2b2-107">SetEnableCustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="5e2b2-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="5e2b2-108">启用和禁用的指定类型的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="5e2b2-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e2b2-109">备注</span><span class="sxs-lookup"><span data-stu-id="5e2b2-109">Remarks</span></span>  
 <span data-ttu-id="5e2b2-110">此接口进行逻辑扩展的 ICorDebugProcess 和 ICorDebugProcess2 接口。</span><span class="sxs-lookup"><span data-stu-id="5e2b2-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e2b2-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="5e2b2-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e2b2-112">要求</span><span class="sxs-lookup"><span data-stu-id="5e2b2-112">Requirements</span></span>  
 <span data-ttu-id="5e2b2-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e2b2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e2b2-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e2b2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e2b2-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e2b2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e2b2-116">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e2b2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e2b2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e2b2-117">See Also</span></span>  
 [<span data-ttu-id="5e2b2-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="5e2b2-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5e2b2-119">调试</span><span class="sxs-lookup"><span data-stu-id="5e2b2-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
