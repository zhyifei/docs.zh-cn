---
title: ICorDebugUnmanagedCallback 接口
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
ms.openlocfilehash: fdd2fee11e9353c3aa3faee2b137597e4ba47801
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791185"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="72d77-102">ICorDebugUnmanagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="72d77-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="72d77-103">提供与公共语言运行时（CLR）不直接相关的本机事件的通知。</span><span class="sxs-lookup"><span data-stu-id="72d77-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72d77-104">方法</span><span class="sxs-lookup"><span data-stu-id="72d77-104">Methods</span></span>  
  
|<span data-ttu-id="72d77-105">方法</span><span class="sxs-lookup"><span data-stu-id="72d77-105">Method</span></span>|<span data-ttu-id="72d77-106">描述</span><span class="sxs-lookup"><span data-stu-id="72d77-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72d77-107">DebugEvent 方法</span><span class="sxs-lookup"><span data-stu-id="72d77-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="72d77-108">通知调试器已激发本机事件。</span><span class="sxs-lookup"><span data-stu-id="72d77-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72d77-109">备注</span><span class="sxs-lookup"><span data-stu-id="72d77-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72d77-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="72d77-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72d77-111">需求</span><span class="sxs-lookup"><span data-stu-id="72d77-111">Requirements</span></span>  
 <span data-ttu-id="72d77-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72d77-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72d77-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72d77-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72d77-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72d77-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72d77-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72d77-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d77-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72d77-116">See also</span></span>

- [<span data-ttu-id="72d77-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="72d77-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
