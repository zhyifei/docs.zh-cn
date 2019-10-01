---
title: ICorDebugCode::GetVersionNumber 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b6fd6e8043f1c62da8994b43a9b9af45fb2e3c0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700824"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="1cf1e-102">ICorDebugCode::GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="1cf1e-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="1cf1e-103">获取一个从1开始的数字，该数字标识此 "ICorDebugCode" 表示的代码版本。</span><span class="sxs-lookup"><span data-stu-id="1cf1e-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="1cf1e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1cf1e-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="1cf1e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1cf1e-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="1cf1e-106">弄指向代码版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="1cf1e-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cf1e-107">备注</span><span class="sxs-lookup"><span data-stu-id="1cf1e-107">Remarks</span></span>

 <span data-ttu-id="1cf1e-108">每次对代码执行 "编辑并继续" （EnC）操作时，版本号都会递增。</span><span class="sxs-lookup"><span data-stu-id="1cf1e-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="1cf1e-109">要求</span><span class="sxs-lookup"><span data-stu-id="1cf1e-109">Requirements</span></span>

 <span data-ttu-id="1cf1e-110">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf1e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cf1e-111">**标头：** Cordebug.idl，Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="1cf1e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cf1e-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cf1e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cf1e-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cf1e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
