---
title: ICorDebugValueEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: 5f95202bd0c8c5045c10378068ae83cad3d93fdd
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396469"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="e6ec1-102">ICorDebugValueEnum 接口</span><span class="sxs-lookup"><span data-stu-id="e6ec1-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="e6ec1-103">实现 "ICorDebugEnum" 方法并枚举 "ICorDebugValue" 数组。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6ec1-104">方法</span><span class="sxs-lookup"><span data-stu-id="e6ec1-104">Methods</span></span>  
  
|<span data-ttu-id="e6ec1-105">方法</span><span class="sxs-lookup"><span data-stu-id="e6ec1-105">Method</span></span>|<span data-ttu-id="e6ec1-106">说明</span><span class="sxs-lookup"><span data-stu-id="e6ec1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6ec1-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="e6ec1-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="e6ec1-108">`ICorDebugValue`从当前位置开始，从枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6ec1-109">备注</span><span class="sxs-lookup"><span data-stu-id="e6ec1-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6ec1-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6ec1-111">要求</span><span class="sxs-lookup"><span data-stu-id="e6ec1-111">Requirements</span></span>  
 <span data-ttu-id="e6ec1-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6ec1-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6ec1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6ec1-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6ec1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6ec1-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6ec1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ec1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6ec1-116">See also</span></span>

- [<span data-ttu-id="e6ec1-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="e6ec1-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
