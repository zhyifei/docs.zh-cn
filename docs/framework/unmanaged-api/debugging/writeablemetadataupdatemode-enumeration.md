---
title: WriteableMetadataUpdateMode 枚举
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
ms.openlocfilehash: 98566176ff33000fc4b4587b5669a037c90268f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139097"
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="ed42b-102">WriteableMetadataUpdateMode 枚举</span><span class="sxs-lookup"><span data-stu-id="ed42b-102">WriteableMetadataUpdateMode Enumeration</span></span>
<span data-ttu-id="ed42b-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="ed42b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ed42b-104">提供用于指定元数据的内存中更新对调试器是否可见的值。</span><span class="sxs-lookup"><span data-stu-id="ed42b-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed42b-105">语法</span><span class="sxs-lookup"><span data-stu-id="ed42b-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="ed42b-106">Members</span><span class="sxs-lookup"><span data-stu-id="ed42b-106">Members</span></span>  
  
|<span data-ttu-id="ed42b-107">成员名称</span><span class="sxs-lookup"><span data-stu-id="ed42b-107">Member name</span></span>|<span data-ttu-id="ed42b-108">描述</span><span class="sxs-lookup"><span data-stu-id="ed42b-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="ed42b-109">当使元数据的内存中更新可见时，保持与 .NET Framework 早期版本的兼容性。</span><span class="sxs-lookup"><span data-stu-id="ed42b-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="ed42b-110">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="ed42b-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="ed42b-111">使元数据的内存中更新对调试器可见。</span><span class="sxs-lookup"><span data-stu-id="ed42b-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed42b-112">备注</span><span class="sxs-lookup"><span data-stu-id="ed42b-112">Remarks</span></span>  
 <span data-ttu-id="ed42b-113">`WriteableMetadataUpdateMode` 枚举的成员可以传递给[SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)方法，以控制目标进程中元数据的内存中更新对调试器是否可见。</span><span class="sxs-lookup"><span data-stu-id="ed42b-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="ed42b-114">`LegacyCompatPolicy` 选项将强制执行与 4.5.2 之前的 .NET Framework 版本相同的行为。</span><span class="sxs-lookup"><span data-stu-id="ed42b-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="ed42b-115">这通常代表更新中的元数据不可见。</span><span class="sxs-lookup"><span data-stu-id="ed42b-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="ed42b-116">但是，对大量调试方法的调用会隐式强迫调试器使更新变得可见。</span><span class="sxs-lookup"><span data-stu-id="ed42b-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="ed42b-117">例如，如果调试器传递了[ICorDebugILFrame：： GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) ，而该方法的原始元数据中找不到该变量的索引，则该模块的所有元数据将更新为与该进程的当前状态匹配的快照。</span><span class="sxs-lookup"><span data-stu-id="ed42b-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="ed42b-118">也就是说，借助 `LegacyCompatPolicy` 选项，调试器可能看不见任何可用的元数据更新，或者可能看见一些或者所有可用的元数据更新，具体取决于它使用非托管调试 API 的其他部分的方式。</span><span class="sxs-lookup"><span data-stu-id="ed42b-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed42b-119">要求</span><span class="sxs-lookup"><span data-stu-id="ed42b-119">Requirements</span></span>  
 <span data-ttu-id="ed42b-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed42b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed42b-121">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed42b-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed42b-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed42b-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed42b-123">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed42b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed42b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed42b-124">See also</span></span>

- [<span data-ttu-id="ed42b-125">调试枚举</span><span class="sxs-lookup"><span data-stu-id="ed42b-125">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="ed42b-126">SetWriteableMetadataUpdateMode 方法</span><span class="sxs-lookup"><span data-stu-id="ed42b-126">SetWriteableMetadataUpdateMode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
