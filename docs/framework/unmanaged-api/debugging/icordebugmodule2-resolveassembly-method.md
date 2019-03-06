---
title: ICorDebugModule2::ResolveAssembly 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359687"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="43946-102">ICorDebugModule2::ResolveAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="43946-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="43946-103">解析指定的元数据标记所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="43946-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="43946-104">语法</span><span class="sxs-lookup"><span data-stu-id="43946-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="43946-105">参数</span><span class="sxs-lookup"><span data-stu-id="43946-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="43946-106">[in]`mdToken`引用程序集的值。</span><span class="sxs-lookup"><span data-stu-id="43946-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="43946-107">[out]指向表示程序集的 icor 调试程序集对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="43946-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="43946-108">备注</span><span class="sxs-lookup"><span data-stu-id="43946-108">Remarks</span></span>

<span data-ttu-id="43946-109">如果该程序集尚未加载时`ResolveAssembly`调用时，HRESULT 返回 CORDBG_E_CANNOT_RESOLVE_ASSEMBLY 的值。</span><span class="sxs-lookup"><span data-stu-id="43946-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="43946-110">要求</span><span class="sxs-lookup"><span data-stu-id="43946-110">Requirements</span></span>

<span data-ttu-id="43946-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43946-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="43946-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43946-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="43946-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43946-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="43946-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43946-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
