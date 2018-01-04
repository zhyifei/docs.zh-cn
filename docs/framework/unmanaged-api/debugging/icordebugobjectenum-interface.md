---
title: "ICorDebugObjectEnum 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectEnum
helpviewer_keywords: ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f2610600d102177c80821c78e7d07f8aed1b6de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectenum-interface1"></a><span data-ttu-id="bc7c4-102">ICorDebugObjectEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="bc7c4-102">ICorDebugObjectEnum Interface1</span></span>
<span data-ttu-id="bc7c4-103">实现 ICorDebugEnum 方法，并通过其相对虚拟地址 (Rva) 枚举对象的数组。</span><span class="sxs-lookup"><span data-stu-id="bc7c4-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc7c4-104">方法</span><span class="sxs-lookup"><span data-stu-id="bc7c4-104">Methods</span></span>  
  
|<span data-ttu-id="bc7c4-105">方法</span><span class="sxs-lookup"><span data-stu-id="bc7c4-105">Method</span></span>|<span data-ttu-id="bc7c4-106">描述</span><span class="sxs-lookup"><span data-stu-id="bc7c4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc7c4-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="bc7c4-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="bc7c4-108">从当前位置开始在枚举中获取指定数目的对象的 Rva。</span><span class="sxs-lookup"><span data-stu-id="bc7c4-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc7c4-109">备注</span><span class="sxs-lookup"><span data-stu-id="bc7c4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc7c4-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="bc7c4-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc7c4-111">惠?</span><span class="sxs-lookup"><span data-stu-id="bc7c4-111">Requirements</span></span>  
 <span data-ttu-id="bc7c4-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc7c4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc7c4-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc7c4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc7c4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc7c4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc7c4-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc7c4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc7c4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc7c4-116">See Also</span></span>  
 [<span data-ttu-id="bc7c4-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="bc7c4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
