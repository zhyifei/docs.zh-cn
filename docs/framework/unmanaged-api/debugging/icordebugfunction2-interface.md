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
ms.openlocfilehash: 5364e39f7e0a9b6c9cd10cd8f17bab4a03a4b7af
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794484"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="fe25c-102">ICorDebugFunction2 接口</span><span class="sxs-lookup"><span data-stu-id="fe25c-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="fe25c-103">对 ICorDebugFunction 接口进行逻辑扩展，以便为跳过非用户代码仅我的代码逐步调试提供支持。</span><span class="sxs-lookup"><span data-stu-id="fe25c-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe25c-104">方法</span><span class="sxs-lookup"><span data-stu-id="fe25c-104">Methods</span></span>  
  
|<span data-ttu-id="fe25c-105">方法</span><span class="sxs-lookup"><span data-stu-id="fe25c-105">Method</span></span>|<span data-ttu-id="fe25c-106">描述</span><span class="sxs-lookup"><span data-stu-id="fe25c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe25c-107">EnumerateNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="fe25c-107">EnumerateNativeCode Method</span></span>](icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="fe25c-108">（尚未实现。）获取一个指向 ICorDebugCodeEnum 的接口指针，该指针包含此 ICorDebugFunction2 对象引用的函数中的本机代码语句。</span><span class="sxs-lookup"><span data-stu-id="fe25c-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="fe25c-109">GetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="fe25c-109">GetJMCStatus Method</span></span>](icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="fe25c-110">获取一个值，该值指示此函数是否被标记为 "用户代码"。</span><span class="sxs-lookup"><span data-stu-id="fe25c-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="fe25c-111">GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="fe25c-111">GetVersionNumber Method</span></span>](icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="fe25c-112">获取此函数的 "编辑并继续" 版本。</span><span class="sxs-lookup"><span data-stu-id="fe25c-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="fe25c-113">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="fe25c-113">SetJMCStatus Method</span></span>](icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="fe25c-114">将此函数标记仅我的代码单步执行。</span><span class="sxs-lookup"><span data-stu-id="fe25c-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe25c-115">备注</span><span class="sxs-lookup"><span data-stu-id="fe25c-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe25c-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="fe25c-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe25c-117">需求</span><span class="sxs-lookup"><span data-stu-id="fe25c-117">Requirements</span></span>  
 <span data-ttu-id="fe25c-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe25c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe25c-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe25c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe25c-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe25c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe25c-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe25c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe25c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe25c-122">See also</span></span>

- [<span data-ttu-id="fe25c-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="fe25c-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
