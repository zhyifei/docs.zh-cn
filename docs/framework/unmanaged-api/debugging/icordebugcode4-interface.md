---
title: ICorDebugCode4 接口
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d23f588b46eb452b7670085249938f7d10cea1ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108157"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="abd1e-102">ICorDebugCode4 接口</span><span class="sxs-lookup"><span data-stu-id="abd1e-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="abd1e-103">提供使调试器能够枚举本地变量和函数中的参数的方法。</span><span class="sxs-lookup"><span data-stu-id="abd1e-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="abd1e-104">方法</span><span class="sxs-lookup"><span data-stu-id="abd1e-104">Methods</span></span>  
  
|<span data-ttu-id="abd1e-105">方法</span><span class="sxs-lookup"><span data-stu-id="abd1e-105">Method</span></span>|<span data-ttu-id="abd1e-106">描述</span><span class="sxs-lookup"><span data-stu-id="abd1e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="abd1e-107">EnumerateVariableHomes 方法</span><span class="sxs-lookup"><span data-stu-id="abd1e-107">EnumerateVariableHomes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="abd1e-108">获取对本地变量和参数的函数中的枚举器。</span><span class="sxs-lookup"><span data-stu-id="abd1e-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abd1e-109">备注</span><span class="sxs-lookup"><span data-stu-id="abd1e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abd1e-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="abd1e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abd1e-111">要求</span><span class="sxs-lookup"><span data-stu-id="abd1e-111">Requirements</span></span>  
 <span data-ttu-id="abd1e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abd1e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abd1e-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="abd1e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="abd1e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abd1e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abd1e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abd1e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd1e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="abd1e-116">See also</span></span>

- [<span data-ttu-id="abd1e-117">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="abd1e-117">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="abd1e-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="abd1e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
