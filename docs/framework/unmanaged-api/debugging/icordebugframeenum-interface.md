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
ms.openlocfilehash: 6cc1ef5f778902efaa53156fbefe334046c82114
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794534"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="f57b3-102">ICorDebugFrameEnum 接口</span><span class="sxs-lookup"><span data-stu-id="f57b3-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="f57b3-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugFrame 数组。</span><span class="sxs-lookup"><span data-stu-id="f57b3-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f57b3-104">方法</span><span class="sxs-lookup"><span data-stu-id="f57b3-104">Methods</span></span>  
  
|<span data-ttu-id="f57b3-105">方法</span><span class="sxs-lookup"><span data-stu-id="f57b3-105">Method</span></span>|<span data-ttu-id="f57b3-106">描述</span><span class="sxs-lookup"><span data-stu-id="f57b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f57b3-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="f57b3-107">Next Method</span></span>](icordebugframeenum-next-method.md)|<span data-ttu-id="f57b3-108">从当前位置开始，从枚举中获取指定数目的 `ICorDebugFrame` 实例。</span><span class="sxs-lookup"><span data-stu-id="f57b3-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f57b3-109">备注</span><span class="sxs-lookup"><span data-stu-id="f57b3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f57b3-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="f57b3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f57b3-111">需求</span><span class="sxs-lookup"><span data-stu-id="f57b3-111">Requirements</span></span>  
 <span data-ttu-id="f57b3-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f57b3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f57b3-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f57b3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f57b3-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f57b3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f57b3-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f57b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57b3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f57b3-116">See also</span></span>

- [<span data-ttu-id="f57b3-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="f57b3-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
