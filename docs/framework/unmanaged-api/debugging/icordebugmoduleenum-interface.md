---
title: ICorDebugModuleEnum Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6086d0a6e915915e8df115dc8b4c4218e77da601
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582326"
---
# <a name="icordebugmoduleenum-interface1"></a><span data-ttu-id="2336b-102">ICorDebugModuleEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="2336b-102">ICorDebugModuleEnum Interface1</span></span>
<span data-ttu-id="2336b-103">实现 ICorDebugEnum 方法，并枚举 icor 调试模块数组。</span><span class="sxs-lookup"><span data-stu-id="2336b-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2336b-104">方法</span><span class="sxs-lookup"><span data-stu-id="2336b-104">Methods</span></span>  
  
|<span data-ttu-id="2336b-105">方法</span><span class="sxs-lookup"><span data-stu-id="2336b-105">Method</span></span>|<span data-ttu-id="2336b-106">描述</span><span class="sxs-lookup"><span data-stu-id="2336b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2336b-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="2336b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="2336b-108">获取指定的数目的`ICorDebugModule`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="2336b-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2336b-109">备注</span><span class="sxs-lookup"><span data-stu-id="2336b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2336b-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2336b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2336b-111">要求</span><span class="sxs-lookup"><span data-stu-id="2336b-111">Requirements</span></span>  
 <span data-ttu-id="2336b-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2336b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2336b-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2336b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2336b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2336b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2336b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2336b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2336b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2336b-116">See also</span></span>
- [<span data-ttu-id="2336b-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="2336b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
