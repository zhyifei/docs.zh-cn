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
ms.openlocfilehash: 0a81f4a53954c559ab12e27bcf039b7b1a1804cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700797"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="ece8c-102">ICorDebugCode::IsIL 方法</span><span class="sxs-lookup"><span data-stu-id="ece8c-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="ece8c-103">获取一个值，该值指示此 "ICorDebugCode" 是否表示使用 Microsoft 中间语言（MSIL）编译的代码。</span><span class="sxs-lookup"><span data-stu-id="ece8c-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="ece8c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ece8c-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="ece8c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ece8c-105">Parameters</span></span>
 `pbIL`  
 <span data-ttu-id="ece8c-106">[out] 如果此 `ICorDebugCode` 表示在 MSIL 中编译的代码，则为 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="ece8c-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ece8c-107">要求</span><span class="sxs-lookup"><span data-stu-id="ece8c-107">Requirements</span></span>

 <span data-ttu-id="ece8c-108">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ece8c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  

 <span data-ttu-id="ece8c-109">**标头：** Cordebug.idl，Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="ece8c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  

 <span data-ttu-id="ece8c-110">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ece8c-110">**Library:** CorGuids.lib</span></span>  

 <span data-ttu-id="ece8c-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ece8c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
 
