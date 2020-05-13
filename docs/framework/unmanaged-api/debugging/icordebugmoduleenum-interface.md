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
ms.openlocfilehash: ccb9eff963da1d502d1ed789640f1a108676754c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213343"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="9b0f5-102">ICorDebugModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="9b0f5-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="9b0f5-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugModule 数组。</span><span class="sxs-lookup"><span data-stu-id="9b0f5-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b0f5-104">方法</span><span class="sxs-lookup"><span data-stu-id="9b0f5-104">Methods</span></span>  
  
|<span data-ttu-id="9b0f5-105">方法</span><span class="sxs-lookup"><span data-stu-id="9b0f5-105">Method</span></span>|<span data-ttu-id="9b0f5-106">描述</span><span class="sxs-lookup"><span data-stu-id="9b0f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b0f5-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="9b0f5-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="9b0f5-108">`ICorDebugModule`从当前位置开始，从枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="9b0f5-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b0f5-109">备注</span><span class="sxs-lookup"><span data-stu-id="9b0f5-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b0f5-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="9b0f5-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b0f5-111">要求</span><span class="sxs-lookup"><span data-stu-id="9b0f5-111">Requirements</span></span>  
 <span data-ttu-id="9b0f5-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b0f5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b0f5-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b0f5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b0f5-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b0f5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b0f5-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b0f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b0f5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b0f5-116">See also</span></span>

- [<span data-ttu-id="9b0f5-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="9b0f5-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
