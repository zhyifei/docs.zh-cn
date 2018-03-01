---
title: "ICorDebugInternalFrame 接口 1"
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
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6e950847764e695f705aeded0e3804db4b872827
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe-interface1"></a><span data-ttu-id="6c3ff-102">ICorDebugInternalFrame 接口 1</span><span class="sxs-lookup"><span data-stu-id="6c3ff-102">ICorDebugInternalFrame Interface1</span></span>
<span data-ttu-id="6c3ff-103">表示在堆栈上的运行时内部帧。</span><span class="sxs-lookup"><span data-stu-id="6c3ff-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="6c3ff-104">此接口是 ICorDebugFrame 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="6c3ff-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c3ff-105">方法</span><span class="sxs-lookup"><span data-stu-id="6c3ff-105">Methods</span></span>  
  
|<span data-ttu-id="6c3ff-106">方法</span><span class="sxs-lookup"><span data-stu-id="6c3ff-106">Method</span></span>|<span data-ttu-id="6c3ff-107">描述</span><span class="sxs-lookup"><span data-stu-id="6c3ff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c3ff-108">GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="6c3ff-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="6c3ff-109">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="6c3ff-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c3ff-110">备注</span><span class="sxs-lookup"><span data-stu-id="6c3ff-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c3ff-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="6c3ff-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c3ff-112">惠?</span><span class="sxs-lookup"><span data-stu-id="6c3ff-112">Requirements</span></span>  
 <span data-ttu-id="6c3ff-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6c3ff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c3ff-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c3ff-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c3ff-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c3ff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c3ff-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c3ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c3ff-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c3ff-117">See Also</span></span>  
 [<span data-ttu-id="6c3ff-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="6c3ff-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
