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
ms.openlocfilehash: dd5baa282d15d121b62b4dc4dd41bcf9ff393570
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395885"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="e273e-102">ICorDebugUnmanagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e273e-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="e273e-103">提供与公共语言运行时（CLR）不直接相关的本机事件的通知。</span><span class="sxs-lookup"><span data-stu-id="e273e-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e273e-104">方法</span><span class="sxs-lookup"><span data-stu-id="e273e-104">Methods</span></span>  
  
|<span data-ttu-id="e273e-105">方法</span><span class="sxs-lookup"><span data-stu-id="e273e-105">Method</span></span>|<span data-ttu-id="e273e-106">说明</span><span class="sxs-lookup"><span data-stu-id="e273e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e273e-107">DebugEvent 方法</span><span class="sxs-lookup"><span data-stu-id="e273e-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="e273e-108">通知调试器已激发本机事件。</span><span class="sxs-lookup"><span data-stu-id="e273e-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e273e-109">备注</span><span class="sxs-lookup"><span data-stu-id="e273e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e273e-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e273e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e273e-111">要求</span><span class="sxs-lookup"><span data-stu-id="e273e-111">Requirements</span></span>  
 <span data-ttu-id="e273e-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e273e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e273e-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e273e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e273e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e273e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e273e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e273e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e273e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e273e-116">See also</span></span>

- [<span data-ttu-id="e273e-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="e273e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
