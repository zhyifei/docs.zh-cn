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
ms.openlocfilehash: 100dc6c83c7c1d45ddb2ea0396c5115c4d79a7f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560355"
---
# <a name="icordebugthreadenum-interface1"></a><span data-ttu-id="97bb8-102">ICorDebugThreadEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="97bb8-102">ICorDebugThreadEnum Interface1</span></span>
<span data-ttu-id="97bb8-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugThread 数组。</span><span class="sxs-lookup"><span data-stu-id="97bb8-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97bb8-104">方法</span><span class="sxs-lookup"><span data-stu-id="97bb8-104">Methods</span></span>  
  
|<span data-ttu-id="97bb8-105">方法</span><span class="sxs-lookup"><span data-stu-id="97bb8-105">Method</span></span>|<span data-ttu-id="97bb8-106">描述</span><span class="sxs-lookup"><span data-stu-id="97bb8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97bb8-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="97bb8-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="97bb8-108">获取指定的数目的`ICorDebugThread`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="97bb8-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97bb8-109">备注</span><span class="sxs-lookup"><span data-stu-id="97bb8-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97bb8-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="97bb8-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97bb8-111">要求</span><span class="sxs-lookup"><span data-stu-id="97bb8-111">Requirements</span></span>  
 <span data-ttu-id="97bb8-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97bb8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97bb8-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97bb8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97bb8-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97bb8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97bb8-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97bb8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97bb8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="97bb8-116">See also</span></span>
- [<span data-ttu-id="97bb8-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="97bb8-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
