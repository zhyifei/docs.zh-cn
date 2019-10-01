---
title: ICorDebugCode::GetFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 825840536968562a53d9e05b8a4628a1df79407d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700833"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="8b58d-102">ICorDebugCode::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="8b58d-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="8b58d-103">获取与此 "ICorDebugCode" 关联的 "ICorDebugFunction"。</span><span class="sxs-lookup"><span data-stu-id="8b58d-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b58d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b58d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b58d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8b58d-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="8b58d-106">弄指向函数的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="8b58d-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b58d-107">备注</span><span class="sxs-lookup"><span data-stu-id="8b58d-107">Remarks</span></span>  
 <span data-ttu-id="8b58d-108">`ICorDebugCode` 和 `ICorDebugFunction` 保持一对一关系。</span><span class="sxs-lookup"><span data-stu-id="8b58d-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b58d-109">要求</span><span class="sxs-lookup"><span data-stu-id="8b58d-109">Requirements</span></span>  
 <span data-ttu-id="8b58d-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b58d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b58d-111">**标头：** Cordebug.idl，Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="8b58d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b58d-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b58d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b58d-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b58d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
