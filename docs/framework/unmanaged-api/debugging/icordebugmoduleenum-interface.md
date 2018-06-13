---
title: ICorDebugModuleEnum 接口 1
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
ms.openlocfilehash: bd6391c06900d5cafc1bfde23bd12c22ee0c77a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422421"
---
# <a name="icordebugmoduleenum-interface1"></a><span data-ttu-id="4e9e0-102">ICorDebugModuleEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="4e9e0-102">ICorDebugModuleEnum Interface1</span></span>
<span data-ttu-id="4e9e0-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugModule 数组。</span><span class="sxs-lookup"><span data-stu-id="4e9e0-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e9e0-104">方法</span><span class="sxs-lookup"><span data-stu-id="4e9e0-104">Methods</span></span>  
  
|<span data-ttu-id="4e9e0-105">方法</span><span class="sxs-lookup"><span data-stu-id="4e9e0-105">Method</span></span>|<span data-ttu-id="4e9e0-106">描述</span><span class="sxs-lookup"><span data-stu-id="4e9e0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e9e0-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="4e9e0-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="4e9e0-108">获取指定的数目的`ICorDebugModule`枚举，从当前位置开始中的实例。</span><span class="sxs-lookup"><span data-stu-id="4e9e0-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e9e0-109">备注</span><span class="sxs-lookup"><span data-stu-id="4e9e0-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e9e0-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4e9e0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e9e0-111">要求</span><span class="sxs-lookup"><span data-stu-id="4e9e0-111">Requirements</span></span>  
 <span data-ttu-id="4e9e0-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e9e0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e9e0-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e9e0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e9e0-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e9e0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e9e0-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e9e0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e9e0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e9e0-116">See Also</span></span>  
 [<span data-ttu-id="4e9e0-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="4e9e0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
