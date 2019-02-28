---
title: ICorDebugFrameEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb1c5bccf43e107cb976016c277c93b146498e1f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978197"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="4d633-102">ICorDebugFrameEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4d633-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="4d633-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugFrame 数组。</span><span class="sxs-lookup"><span data-stu-id="4d633-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d633-104">方法</span><span class="sxs-lookup"><span data-stu-id="4d633-104">Methods</span></span>  
  
|<span data-ttu-id="4d633-105">方法</span><span class="sxs-lookup"><span data-stu-id="4d633-105">Method</span></span>|<span data-ttu-id="4d633-106">描述</span><span class="sxs-lookup"><span data-stu-id="4d633-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d633-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="4d633-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="4d633-108">获取指定的数目的`ICorDebugFrame`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="4d633-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d633-109">备注</span><span class="sxs-lookup"><span data-stu-id="4d633-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d633-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4d633-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d633-111">要求</span><span class="sxs-lookup"><span data-stu-id="4d633-111">Requirements</span></span>  
 <span data-ttu-id="4d633-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d633-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d633-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d633-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d633-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d633-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d633-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d633-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d633-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d633-116">See also</span></span>
- [<span data-ttu-id="4d633-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="4d633-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
