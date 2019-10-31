---
title: ICorDebugModule2::ApplyChanges 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
ms.openlocfilehash: c324019e1e62701f4f2aaba1c00948b292ba6847
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127914"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="b1eae-102">ICorDebugModule2::ApplyChanges 方法</span><span class="sxs-lookup"><span data-stu-id="b1eae-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="b1eae-103">将元数据中的更改和 Microsoft 中间语言（MSIL）代码的更改应用到正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="b1eae-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1eae-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1eae-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1eae-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1eae-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="b1eae-106">中增量元数据的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b1eae-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="b1eae-107">中包含增量元数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b1eae-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="b1eae-108">缓冲区的地址从[IMetaDataEmit2：： SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="b1eae-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="b1eae-109">元数据中的相对虚拟地址（Rva）应相对于 MSIL 代码的开头。</span><span class="sxs-lookup"><span data-stu-id="b1eae-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="b1eae-110">中增量 MSIL 代码的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b1eae-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="b1eae-111">中包含更新的 MSIL 代码的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b1eae-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1eae-112">备注</span><span class="sxs-lookup"><span data-stu-id="b1eae-112">Remarks</span></span>  
 <span data-ttu-id="b1eae-113">`pbMetadata` 参数采用特殊增量元数据格式（如[IMetaDataEmit2：： SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)输出）。</span><span class="sxs-lookup"><span data-stu-id="b1eae-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="b1eae-114">`pbMetadata` 将以前的元数据作为基础，并描述要应用于该基的单个更改。</span><span class="sxs-lookup"><span data-stu-id="b1eae-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="b1eae-115">与此相反，`pbIL[`] 参数包含更新方法的新 MSIL，并旨在完全替换该方法的以前的 MSIL</span><span class="sxs-lookup"><span data-stu-id="b1eae-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="b1eae-116">当在调试器内存中创建了增量 MSIL 和元数据时，调试器会调用 `ApplyChanges` 将更改发送到公共语言运行时（CLR）。</span><span class="sxs-lookup"><span data-stu-id="b1eae-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="b1eae-117">运行时将更新其元数据表，将新的 MSIL 置于进程中，并设置新 MSIL 的实时（JIT）编译。</span><span class="sxs-lookup"><span data-stu-id="b1eae-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="b1eae-118">应用这些更改后，调试器应调用[IMetaDataEmit2：： ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)来准备下一个编辑会话。</span><span class="sxs-lookup"><span data-stu-id="b1eae-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="b1eae-119">然后，调试器可以继续执行该过程。</span><span class="sxs-lookup"><span data-stu-id="b1eae-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="b1eae-120">每当调试器调用具有增量元数据的模块上的 `ApplyChanges` 时，它还应在该模块的元数据的所有副本上调用具有相同增量元数据的[IMetaDataEmit：： ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) （用于发出更改的副本除外）。</span><span class="sxs-lookup"><span data-stu-id="b1eae-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="b1eae-121">如果元数据的副本在某种程度上与实际的元数据不同步，则调试器始终可以丢弃该复制并获取新副本。</span><span class="sxs-lookup"><span data-stu-id="b1eae-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="b1eae-122">如果 `ApplyChanges` 方法失败，调试会话将处于无效状态，必须重新启动。</span><span class="sxs-lookup"><span data-stu-id="b1eae-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1eae-123">要求</span><span class="sxs-lookup"><span data-stu-id="b1eae-123">Requirements</span></span>  
 <span data-ttu-id="b1eae-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1eae-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1eae-125">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1eae-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1eae-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1eae-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1eae-127">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1eae-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
