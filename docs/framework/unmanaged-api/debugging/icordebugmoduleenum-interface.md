---
title: ICorDebugModuleEnum 接口
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
ms.openlocfilehash: 682fe190126d4f40013678d996804e9f3481bc02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965086"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="06251-102">ICorDebugModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="06251-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="06251-103">实现 ICorDebugEnum 方法, 并枚举 ICorDebugModule 数组。</span><span class="sxs-lookup"><span data-stu-id="06251-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06251-104">方法</span><span class="sxs-lookup"><span data-stu-id="06251-104">Methods</span></span>  
  
|<span data-ttu-id="06251-105">方法</span><span class="sxs-lookup"><span data-stu-id="06251-105">Method</span></span>|<span data-ttu-id="06251-106">描述</span><span class="sxs-lookup"><span data-stu-id="06251-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06251-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="06251-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="06251-108">从当前位置开始, 从`ICorDebugModule`枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="06251-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06251-109">备注</span><span class="sxs-lookup"><span data-stu-id="06251-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06251-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="06251-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06251-111">要求</span><span class="sxs-lookup"><span data-stu-id="06251-111">Requirements</span></span>  
 <span data-ttu-id="06251-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06251-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06251-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="06251-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06251-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06251-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06251-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06251-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06251-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="06251-116">See also</span></span>

- [<span data-ttu-id="06251-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="06251-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
