---
title: ICorDebugTypeEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum
helpviewer_keywords:
- ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: 159ccfcf-b37c-4ad9-8e0d-a9a443262472
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b81230ee901510b2859b45de76c6dcfa6cb28e58
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968182"
---
# <a name="icordebugtypeenum-interface"></a><span data-ttu-id="e2881-102">ICorDebugTypeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="e2881-102">ICorDebugTypeEnum Interface</span></span>
<span data-ttu-id="e2881-103">实现 "ICorDebugEnum" 方法并枚举 "ICorDebugType" 数组。</span><span class="sxs-lookup"><span data-stu-id="e2881-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugType" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2881-104">方法</span><span class="sxs-lookup"><span data-stu-id="e2881-104">Methods</span></span>  
  
|<span data-ttu-id="e2881-105">方法</span><span class="sxs-lookup"><span data-stu-id="e2881-105">Method</span></span>|<span data-ttu-id="e2881-106">描述</span><span class="sxs-lookup"><span data-stu-id="e2881-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2881-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="e2881-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-next-method.md)|<span data-ttu-id="e2881-108">从当前位置开始, 从`ICorDebugType`枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="e2881-108">Gets the specified number of `ICorDebugType` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2881-109">备注</span><span class="sxs-lookup"><span data-stu-id="e2881-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2881-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e2881-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2881-111">要求</span><span class="sxs-lookup"><span data-stu-id="e2881-111">Requirements</span></span>  
 <span data-ttu-id="e2881-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2881-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2881-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="e2881-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2881-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2881-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2881-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2881-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2881-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2881-116">See also</span></span>

- [<span data-ttu-id="e2881-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="e2881-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
