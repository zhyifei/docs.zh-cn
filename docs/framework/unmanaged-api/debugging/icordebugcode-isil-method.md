---
title: ICorDebugCode::IsIL 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b7cbadbd1494d5e4d1488dd12296f4f90890127
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395484"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="bb70a-102">ICorDebugCode::IsIL 方法</span><span class="sxs-lookup"><span data-stu-id="bb70a-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="bb70a-103">获取一个值，该值指示此 "ICorDebugCode" 是否表示使用 Microsoft 中间语言（MSIL）编译的代码。</span><span class="sxs-lookup"><span data-stu-id="bb70a-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="bb70a-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb70a-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="bb70a-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb70a-105">Parameters</span></span>

`pbIL`  
<span data-ttu-id="bb70a-106">[out] 如果此 `ICorDebugCode` 表示在 MSIL 中编译的代码，则为 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="bb70a-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb70a-107">要求</span><span class="sxs-lookup"><span data-stu-id="bb70a-107">Requirements</span></span>

<span data-ttu-id="bb70a-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb70a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bb70a-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb70a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="bb70a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb70a-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="bb70a-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb70a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
