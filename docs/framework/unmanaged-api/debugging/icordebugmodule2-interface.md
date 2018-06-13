---
title: ICorDebugModule2 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 537023cf117477b54117799fc9ea62e894bb6591
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419135"
---
# <a name="icordebugmodule2-interface1"></a><span data-ttu-id="f34e5-102">ICorDebugModule2 接口 1</span><span class="sxs-lookup"><span data-stu-id="f34e5-102">ICorDebugModule2 Interface1</span></span>
<span data-ttu-id="f34e5-103">用作 ICorDebugModule 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="f34e5-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f34e5-104">方法</span><span class="sxs-lookup"><span data-stu-id="f34e5-104">Methods</span></span>  
  
|<span data-ttu-id="f34e5-105">方法</span><span class="sxs-lookup"><span data-stu-id="f34e5-105">Method</span></span>|<span data-ttu-id="f34e5-106">描述</span><span class="sxs-lookup"><span data-stu-id="f34e5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f34e5-107">ApplyChanges 方法</span><span class="sxs-lookup"><span data-stu-id="f34e5-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="f34e5-108">适用于正在运行的进程中元数据的更改和 Microsoft 中间语言 (MSIL) 代码中的更改。</span><span class="sxs-lookup"><span data-stu-id="f34e5-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="f34e5-109">GetJITCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="f34e5-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="f34e5-110">获取控制此实时 (JIT) 编译的标志`ICorDebugModule2`。</span><span class="sxs-lookup"><span data-stu-id="f34e5-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="f34e5-111">ResolveAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="f34e5-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="f34e5-112">解析指定的元数据标记所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="f34e5-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="f34e5-113">SetJITCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="f34e5-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="f34e5-114">设置用于控制此 JIT 编译的标志`ICorDebugModule2`。</span><span class="sxs-lookup"><span data-stu-id="f34e5-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="f34e5-115">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="f34e5-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="f34e5-116">在此设置的所有类的所有方法的仅我的代码 (JMC) 状态`ICorDebugModule2`为指定的值，除中`pTokens`数组，它将设置为的相反值。</span><span class="sxs-lookup"><span data-stu-id="f34e5-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f34e5-117">备注</span><span class="sxs-lookup"><span data-stu-id="f34e5-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f34e5-118">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="f34e5-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f34e5-119">要求</span><span class="sxs-lookup"><span data-stu-id="f34e5-119">Requirements</span></span>  
 <span data-ttu-id="f34e5-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f34e5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f34e5-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f34e5-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f34e5-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f34e5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f34e5-123">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f34e5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f34e5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f34e5-124">See Also</span></span>  
 [<span data-ttu-id="f34e5-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="f34e5-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
