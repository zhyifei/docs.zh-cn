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
ms.openlocfilehash: 0809a149a5a5a5e9adea059140d7b4b456337ef3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125302"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="688ce-102">ICorDebugModule2::ResolveAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="688ce-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="688ce-103">解析指定的元数据标记所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="688ce-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="688ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="688ce-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="688ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="688ce-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="688ce-106">中引用程序集的 `mdToken` 值。</span><span class="sxs-lookup"><span data-stu-id="688ce-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="688ce-107">弄指向表示程序集的 ICorDebugAssembly 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="688ce-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="688ce-108">备注</span><span class="sxs-lookup"><span data-stu-id="688ce-108">Remarks</span></span>

<span data-ttu-id="688ce-109">如果在调用 `ResolveAssembly` 时尚未加载该程序集，则返回 CORDBG_E_CANNOT_RESOLVE_ASSEMBLY 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="688ce-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="688ce-110">要求</span><span class="sxs-lookup"><span data-stu-id="688ce-110">Requirements</span></span>

<span data-ttu-id="688ce-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="688ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="688ce-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="688ce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="688ce-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="688ce-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="688ce-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="688ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
