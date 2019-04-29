---
title: ICorDebugFunction2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 159cebc76f732629ed84a3b6c9041cc15f8bbb69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763758"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="1da36-102">ICorDebugFunction2 接口</span><span class="sxs-lookup"><span data-stu-id="1da36-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="1da36-103">合理扩展 ICorDebugFunction 接口，以提供支持仅我的代码单步调试，这样可以跳过非用户代码。</span><span class="sxs-lookup"><span data-stu-id="1da36-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1da36-104">方法</span><span class="sxs-lookup"><span data-stu-id="1da36-104">Methods</span></span>  
  
|<span data-ttu-id="1da36-105">方法</span><span class="sxs-lookup"><span data-stu-id="1da36-105">Method</span></span>|<span data-ttu-id="1da36-106">描述</span><span class="sxs-lookup"><span data-stu-id="1da36-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1da36-107">EnumerateNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="1da36-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="1da36-108">（尚未实现。）获取包含此 ICorDebugFunction2 对象引用的函数中的本机代码语句 ICorDebugCodeEnum 接口指针。</span><span class="sxs-lookup"><span data-stu-id="1da36-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="1da36-109">GetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="1da36-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="1da36-110">获取一个值，该值指示此函数是否被标记为用户代码。</span><span class="sxs-lookup"><span data-stu-id="1da36-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="1da36-111">GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="1da36-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="1da36-112">获取此函数的编辑并继续版本。</span><span class="sxs-lookup"><span data-stu-id="1da36-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="1da36-113">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="1da36-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="1da36-114">将此函数标记为仅我的代码单步执行。</span><span class="sxs-lookup"><span data-stu-id="1da36-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1da36-115">备注</span><span class="sxs-lookup"><span data-stu-id="1da36-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1da36-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1da36-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1da36-117">要求</span><span class="sxs-lookup"><span data-stu-id="1da36-117">Requirements</span></span>  
 <span data-ttu-id="1da36-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1da36-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1da36-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1da36-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1da36-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1da36-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1da36-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1da36-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da36-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="1da36-122">See also</span></span>

- [<span data-ttu-id="1da36-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="1da36-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
