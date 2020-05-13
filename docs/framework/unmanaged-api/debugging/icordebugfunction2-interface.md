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
ms.openlocfilehash: 611091d39da6d7f646457457f20ce1eaf37db361
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213200"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="104eb-102">ICorDebugFunction2 接口</span><span class="sxs-lookup"><span data-stu-id="104eb-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="104eb-103">对 ICorDebugFunction 接口进行逻辑扩展，以便为跳过非用户代码仅我的代码逐步调试提供支持。</span><span class="sxs-lookup"><span data-stu-id="104eb-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="104eb-104">方法</span><span class="sxs-lookup"><span data-stu-id="104eb-104">Methods</span></span>  
  
|<span data-ttu-id="104eb-105">方法</span><span class="sxs-lookup"><span data-stu-id="104eb-105">Method</span></span>|<span data-ttu-id="104eb-106">描述</span><span class="sxs-lookup"><span data-stu-id="104eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="104eb-107">EnumerateNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="104eb-107">EnumerateNativeCode Method</span></span>](icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="104eb-108">（尚未实现。）获取一个指向 ICorDebugCodeEnum 的接口指针，该指针包含此 ICorDebugFunction2 对象引用的函数中的本机代码语句。</span><span class="sxs-lookup"><span data-stu-id="104eb-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="104eb-109">GetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="104eb-109">GetJMCStatus Method</span></span>](icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="104eb-110">获取一个值，该值指示此函数是否被标记为 "用户代码"。</span><span class="sxs-lookup"><span data-stu-id="104eb-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="104eb-111">GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="104eb-111">GetVersionNumber Method</span></span>](icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="104eb-112">获取此函数的 "编辑并继续" 版本。</span><span class="sxs-lookup"><span data-stu-id="104eb-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="104eb-113">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="104eb-113">SetJMCStatus Method</span></span>](icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="104eb-114">将此函数标记仅我的代码单步执行。</span><span class="sxs-lookup"><span data-stu-id="104eb-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="104eb-115">备注</span><span class="sxs-lookup"><span data-stu-id="104eb-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="104eb-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="104eb-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="104eb-117">要求</span><span class="sxs-lookup"><span data-stu-id="104eb-117">Requirements</span></span>  
 <span data-ttu-id="104eb-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="104eb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="104eb-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="104eb-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="104eb-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="104eb-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="104eb-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="104eb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="104eb-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="104eb-122">See also</span></span>

- [<span data-ttu-id="104eb-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="104eb-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
