---
title: ICorDebugModule2 接口
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
ms.openlocfilehash: 7b98302985d9d54599ea8ea2e01dc2503c468d58
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210223"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="e8b78-102">ICorDebugModule2 接口</span><span class="sxs-lookup"><span data-stu-id="e8b78-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="e8b78-103">用作 ICorDebugModule 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="e8b78-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8b78-104">方法</span><span class="sxs-lookup"><span data-stu-id="e8b78-104">Methods</span></span>  
  
|<span data-ttu-id="e8b78-105">方法</span><span class="sxs-lookup"><span data-stu-id="e8b78-105">Method</span></span>|<span data-ttu-id="e8b78-106">描述</span><span class="sxs-lookup"><span data-stu-id="e8b78-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8b78-107">ApplyChanges 方法</span><span class="sxs-lookup"><span data-stu-id="e8b78-107">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="e8b78-108">将元数据中的更改和 Microsoft 中间语言（MSIL）代码的更改应用到正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="e8b78-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="e8b78-109">GetJITCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="e8b78-109">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="e8b78-110">获取用于控制此的实时（JIT）编译的标志 `ICorDebugModule2` 。</span><span class="sxs-lookup"><span data-stu-id="e8b78-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="e8b78-111">ResolveAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="e8b78-111">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="e8b78-112">解析指定的元数据标记所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="e8b78-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="e8b78-113">SetJITCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="e8b78-113">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="e8b78-114">设置控制此的 JIT 编译的标志 `ICorDebugModule2` 。</span><span class="sxs-lookup"><span data-stu-id="e8b78-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="e8b78-115">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="e8b78-115">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="e8b78-116">将此中所有类的所有方法的仅我的代码（JMC）状态设置 `ICorDebugModule2` 为指定的值（数组中的所有方法除外 `pTokens` ，将其设置为相反的值）。</span><span class="sxs-lookup"><span data-stu-id="e8b78-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8b78-117">备注</span><span class="sxs-lookup"><span data-stu-id="e8b78-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8b78-118">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e8b78-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8b78-119">要求</span><span class="sxs-lookup"><span data-stu-id="e8b78-119">Requirements</span></span>  
 <span data-ttu-id="e8b78-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8b78-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8b78-121">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8b78-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8b78-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8b78-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8b78-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b78-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b78-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8b78-124">See also</span></span>

- [<span data-ttu-id="e8b78-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="e8b78-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
