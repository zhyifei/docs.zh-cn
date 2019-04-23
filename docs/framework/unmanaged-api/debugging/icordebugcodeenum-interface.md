---
title: ICorDebugCodeEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f36ce2fbf57c72102550069989c94b5cc19e58c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186649"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="4d757-102">ICorDebugCodeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4d757-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="4d757-103">实现"ICorDebugEnum"方法，并枚举"ICorDebugCode"数组。</span><span class="sxs-lookup"><span data-stu-id="4d757-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d757-104">方法</span><span class="sxs-lookup"><span data-stu-id="4d757-104">Methods</span></span>  
  
|<span data-ttu-id="4d757-105">方法</span><span class="sxs-lookup"><span data-stu-id="4d757-105">Method</span></span>|<span data-ttu-id="4d757-106">描述</span><span class="sxs-lookup"><span data-stu-id="4d757-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d757-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="4d757-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="4d757-108">获取指定的数目的`ICorDebugCode`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="4d757-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d757-109">备注</span><span class="sxs-lookup"><span data-stu-id="4d757-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d757-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4d757-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d757-111">要求</span><span class="sxs-lookup"><span data-stu-id="4d757-111">Requirements</span></span>  
 <span data-ttu-id="4d757-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d757-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d757-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d757-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d757-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d757-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d757-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d757-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d757-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d757-116">See also</span></span>

- [<span data-ttu-id="4d757-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="4d757-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
