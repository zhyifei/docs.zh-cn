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
ms.openlocfilehash: 26efb3e43642b6d1fd10b084c2b321609c89d89b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994677"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="b84fc-102">ICorDebugModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b84fc-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="b84fc-103">实现 ICorDebugEnum 方法，并枚举 icor 调试模块数组。</span><span class="sxs-lookup"><span data-stu-id="b84fc-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b84fc-104">方法</span><span class="sxs-lookup"><span data-stu-id="b84fc-104">Methods</span></span>  
  
|<span data-ttu-id="b84fc-105">方法</span><span class="sxs-lookup"><span data-stu-id="b84fc-105">Method</span></span>|<span data-ttu-id="b84fc-106">描述</span><span class="sxs-lookup"><span data-stu-id="b84fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b84fc-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="b84fc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="b84fc-108">获取指定的数目的`ICorDebugModule`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="b84fc-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b84fc-109">备注</span><span class="sxs-lookup"><span data-stu-id="b84fc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b84fc-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="b84fc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b84fc-111">要求</span><span class="sxs-lookup"><span data-stu-id="b84fc-111">Requirements</span></span>  
 <span data-ttu-id="b84fc-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b84fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b84fc-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b84fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b84fc-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b84fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b84fc-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b84fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84fc-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b84fc-116">See also</span></span>

- [<span data-ttu-id="b84fc-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="b84fc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
