---
title: ICorDebugThreadEnum 接口
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
ms.openlocfilehash: 6de2cb7c1a1423c5bd38a6f2e5d01c39166ab119
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791322"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="89e9f-102">ICorDebugThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="89e9f-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="89e9f-103">实现 ICorDebugEnum 方法并枚举 ICorDebugThread 数组。</span><span class="sxs-lookup"><span data-stu-id="89e9f-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89e9f-104">方法</span><span class="sxs-lookup"><span data-stu-id="89e9f-104">Methods</span></span>  
  
|<span data-ttu-id="89e9f-105">方法</span><span class="sxs-lookup"><span data-stu-id="89e9f-105">Method</span></span>|<span data-ttu-id="89e9f-106">描述</span><span class="sxs-lookup"><span data-stu-id="89e9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89e9f-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="89e9f-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="89e9f-108">从当前位置开始，从枚举中获取指定数目的 `ICorDebugThread` 实例。</span><span class="sxs-lookup"><span data-stu-id="89e9f-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89e9f-109">备注</span><span class="sxs-lookup"><span data-stu-id="89e9f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89e9f-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="89e9f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e9f-111">需求</span><span class="sxs-lookup"><span data-stu-id="89e9f-111">Requirements</span></span>  
 <span data-ttu-id="89e9f-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89e9f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e9f-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89e9f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89e9f-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89e9f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89e9f-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e9f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e9f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89e9f-116">See also</span></span>

- [<span data-ttu-id="89e9f-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="89e9f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
