---
title: ICorDebugCode2::GetCompilerFlags 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
ms.openlocfilehash: d948fda048e724ad11c59bf7d4776ee2ca6c8d58
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125545"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="9c112-102">ICorDebugCode2::GetCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="9c112-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="9c112-103">获取标志，这些标志指定此代码对象是实时（JIT）编译或使用本机映像生成器（Ngen.exe）生成的。</span><span class="sxs-lookup"><span data-stu-id="9c112-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="9c112-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c112-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="9c112-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c112-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="9c112-106">弄指向[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)枚举的值的指针，该枚举指定 JIT 编译器或本机图像生成器的行为。</span><span class="sxs-lookup"><span data-stu-id="9c112-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c112-107">要求</span><span class="sxs-lookup"><span data-stu-id="9c112-107">Requirements</span></span>

<span data-ttu-id="9c112-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c112-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9c112-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c112-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="9c112-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c112-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9c112-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c112-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
