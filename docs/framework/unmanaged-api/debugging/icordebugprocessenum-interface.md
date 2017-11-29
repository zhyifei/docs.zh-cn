---
title: "ICorDebugProcessEnum 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcessEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcessEnum
helpviewer_keywords: ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 255107738c3ab6dafbbd81d0839a671f9621cf4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessenum-interface1"></a><span data-ttu-id="9b8e3-102">ICorDebugProcessEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="9b8e3-102">ICorDebugProcessEnum Interface1</span></span>
<span data-ttu-id="9b8e3-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugProcess 数组。</span><span class="sxs-lookup"><span data-stu-id="9b8e3-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b8e3-104">方法</span><span class="sxs-lookup"><span data-stu-id="9b8e3-104">Methods</span></span>  
  
|<span data-ttu-id="9b8e3-105">方法</span><span class="sxs-lookup"><span data-stu-id="9b8e3-105">Method</span></span>|<span data-ttu-id="9b8e3-106">描述</span><span class="sxs-lookup"><span data-stu-id="9b8e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b8e3-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="9b8e3-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-next-method.md)|<span data-ttu-id="9b8e3-108">获取指定的数目的`ICorDebugProcess`枚举，从当前位置开始中的实例。</span><span class="sxs-lookup"><span data-stu-id="9b8e3-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b8e3-109">备注</span><span class="sxs-lookup"><span data-stu-id="9b8e3-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b8e3-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="9b8e3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b8e3-111">要求</span><span class="sxs-lookup"><span data-stu-id="9b8e3-111">Requirements</span></span>  
 <span data-ttu-id="9b8e3-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b8e3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b8e3-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b8e3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b8e3-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b8e3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b8e3-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b8e3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8e3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b8e3-116">See Also</span></span>  
 [<span data-ttu-id="9b8e3-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="9b8e3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
