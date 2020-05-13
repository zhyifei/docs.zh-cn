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
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210016"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="8dd32-102">ICorDebugModule2::ResolveAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="8dd32-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="8dd32-103">解析指定的元数据标记所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="8dd32-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="8dd32-104">语法</span><span class="sxs-lookup"><span data-stu-id="8dd32-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="8dd32-105">参数</span><span class="sxs-lookup"><span data-stu-id="8dd32-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="8dd32-106">中一个 `mdToken` 引用程序集的值。</span><span class="sxs-lookup"><span data-stu-id="8dd32-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="8dd32-107">弄指向表示程序集的 ICorDebugAssembly 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="8dd32-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="8dd32-108">备注</span><span class="sxs-lookup"><span data-stu-id="8dd32-108">Remarks</span></span>

<span data-ttu-id="8dd32-109">如果在调用时尚未加载该程序集 `ResolveAssembly` ，则将返回 CORDBG_E_CANNOT_RESOLVE_ASSEMBLY 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="8dd32-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="8dd32-110">要求</span><span class="sxs-lookup"><span data-stu-id="8dd32-110">Requirements</span></span>

<span data-ttu-id="8dd32-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8dd32-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="8dd32-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dd32-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="8dd32-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dd32-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8dd32-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dd32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
