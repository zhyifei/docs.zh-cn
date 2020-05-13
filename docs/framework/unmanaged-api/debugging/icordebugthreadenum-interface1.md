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
ms.openlocfilehash: 82a7689bb1848d89f5dee4482d8dc7685c9c5b5c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378334"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="e05d4-102">ICorDebugThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="e05d4-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="e05d4-103">实现 ICorDebugEnum 方法并枚举 ICorDebugThread 数组。</span><span class="sxs-lookup"><span data-stu-id="e05d4-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e05d4-104">方法</span><span class="sxs-lookup"><span data-stu-id="e05d4-104">Methods</span></span>  
  
|<span data-ttu-id="e05d4-105">方法</span><span class="sxs-lookup"><span data-stu-id="e05d4-105">Method</span></span>|<span data-ttu-id="e05d4-106">描述</span><span class="sxs-lookup"><span data-stu-id="e05d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e05d4-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="e05d4-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="e05d4-108">`ICorDebugThread`从当前位置开始，从枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="e05d4-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e05d4-109">备注</span><span class="sxs-lookup"><span data-stu-id="e05d4-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e05d4-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e05d4-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e05d4-111">要求</span><span class="sxs-lookup"><span data-stu-id="e05d4-111">Requirements</span></span>  
 <span data-ttu-id="e05d4-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e05d4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e05d4-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e05d4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e05d4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e05d4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e05d4-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e05d4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05d4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e05d4-116">See also</span></span>

- [<span data-ttu-id="e05d4-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="e05d4-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
