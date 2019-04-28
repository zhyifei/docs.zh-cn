---
title: ICorDebugHeapValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5fcd8c17c4006714fa9d11aece5cccc57c97087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700821"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="2c29e-102">ICorDebugHeapValue 接口</span><span class="sxs-lookup"><span data-stu-id="2c29e-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="2c29e-103">表示由公共语言运行时 (CLR) 垃圾回收器收集的对象的"ICorDebugValue"的子类。</span><span class="sxs-lookup"><span data-stu-id="2c29e-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c29e-104">方法</span><span class="sxs-lookup"><span data-stu-id="2c29e-104">Methods</span></span>  
  
|<span data-ttu-id="2c29e-105">方法</span><span class="sxs-lookup"><span data-stu-id="2c29e-105">Method</span></span>|<span data-ttu-id="2c29e-106">描述</span><span class="sxs-lookup"><span data-stu-id="2c29e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c29e-107">CreateRelocBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="2c29e-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="2c29e-108">未实现。</span><span class="sxs-lookup"><span data-stu-id="2c29e-108">Not implemented.</span></span>|  
|[<span data-ttu-id="2c29e-109">IsValid 方法</span><span class="sxs-lookup"><span data-stu-id="2c29e-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="2c29e-110">获取一个值，指示该对象表示由此`ICorDebugHeapValue`是有效的或已由垃圾回收器收回。</span><span class="sxs-lookup"><span data-stu-id="2c29e-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="2c29e-111">.NET Framework 2.0 版中，此方法已弃用。</span><span class="sxs-lookup"><span data-stu-id="2c29e-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c29e-112">备注</span><span class="sxs-lookup"><span data-stu-id="2c29e-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c29e-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2c29e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c29e-114">要求</span><span class="sxs-lookup"><span data-stu-id="2c29e-114">Requirements</span></span>  
 <span data-ttu-id="2c29e-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c29e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c29e-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c29e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c29e-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c29e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c29e-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c29e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c29e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c29e-119">See also</span></span>

- [<span data-ttu-id="2c29e-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="2c29e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
