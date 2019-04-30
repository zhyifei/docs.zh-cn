---
title: ICorDebugThreadEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7edf103e397c6e3e1577b5ed4bc8fc0df264b843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993845"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="a29bc-102">ICorDebugThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="a29bc-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="a29bc-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugThread 数组。</span><span class="sxs-lookup"><span data-stu-id="a29bc-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a29bc-104">方法</span><span class="sxs-lookup"><span data-stu-id="a29bc-104">Methods</span></span>  
  
|<span data-ttu-id="a29bc-105">方法</span><span class="sxs-lookup"><span data-stu-id="a29bc-105">Method</span></span>|<span data-ttu-id="a29bc-106">描述</span><span class="sxs-lookup"><span data-stu-id="a29bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a29bc-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="a29bc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="a29bc-108">获取指定的数目的`ICorDebugThread`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="a29bc-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a29bc-109">备注</span><span class="sxs-lookup"><span data-stu-id="a29bc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a29bc-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a29bc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a29bc-111">要求</span><span class="sxs-lookup"><span data-stu-id="a29bc-111">Requirements</span></span>  
 <span data-ttu-id="a29bc-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a29bc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a29bc-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a29bc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a29bc-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a29bc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a29bc-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a29bc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a29bc-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a29bc-116">See also</span></span>

- [<span data-ttu-id="a29bc-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="a29bc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
