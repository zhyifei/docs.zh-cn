---
title: "ICorDebugUnmanagedCallback 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnmanagedCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnmanagedCallback
helpviewer_keywords: ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa104bee5171b3b28731cf18a4d26e32f49169ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="89861-102">ICorDebugUnmanagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="89861-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="89861-103">提供与公共语言运行时 (CLR) 不直接相关的本机事件的通知。</span><span class="sxs-lookup"><span data-stu-id="89861-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89861-104">方法</span><span class="sxs-lookup"><span data-stu-id="89861-104">Methods</span></span>  
  
|<span data-ttu-id="89861-105">方法</span><span class="sxs-lookup"><span data-stu-id="89861-105">Method</span></span>|<span data-ttu-id="89861-106">描述</span><span class="sxs-lookup"><span data-stu-id="89861-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89861-107">DebugEvent 方法</span><span class="sxs-lookup"><span data-stu-id="89861-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="89861-108">通知调试器已激发本机事件。</span><span class="sxs-lookup"><span data-stu-id="89861-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89861-109">备注</span><span class="sxs-lookup"><span data-stu-id="89861-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89861-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="89861-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89861-111">要求</span><span class="sxs-lookup"><span data-stu-id="89861-111">Requirements</span></span>  
 <span data-ttu-id="89861-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89861-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89861-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89861-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89861-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89861-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89861-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89861-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89861-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89861-116">See Also</span></span>  
 [<span data-ttu-id="89861-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="89861-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
