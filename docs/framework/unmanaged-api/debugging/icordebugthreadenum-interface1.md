---
title: ICorDebugThreadEnum 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca683e5925325fae2470aca3cd67be39c12a055d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423268"
---
# <a name="icordebugthreadenum-interface1"></a><span data-ttu-id="7dd3c-102">ICorDebugThreadEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="7dd3c-102">ICorDebugThreadEnum Interface1</span></span>
<span data-ttu-id="7dd3c-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugThread 数组。</span><span class="sxs-lookup"><span data-stu-id="7dd3c-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7dd3c-104">方法</span><span class="sxs-lookup"><span data-stu-id="7dd3c-104">Methods</span></span>  
  
|<span data-ttu-id="7dd3c-105">方法</span><span class="sxs-lookup"><span data-stu-id="7dd3c-105">Method</span></span>|<span data-ttu-id="7dd3c-106">描述</span><span class="sxs-lookup"><span data-stu-id="7dd3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7dd3c-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="7dd3c-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="7dd3c-108">获取指定的数目的`ICorDebugThread`枚举，从当前位置开始中的实例。</span><span class="sxs-lookup"><span data-stu-id="7dd3c-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dd3c-109">备注</span><span class="sxs-lookup"><span data-stu-id="7dd3c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dd3c-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="7dd3c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dd3c-111">要求</span><span class="sxs-lookup"><span data-stu-id="7dd3c-111">Requirements</span></span>  
 <span data-ttu-id="7dd3c-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7dd3c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dd3c-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7dd3c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7dd3c-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dd3c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dd3c-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dd3c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd3c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dd3c-116">See Also</span></span>  
 [<span data-ttu-id="7dd3c-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="7dd3c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
