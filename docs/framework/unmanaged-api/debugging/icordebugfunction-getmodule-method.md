---
title: ICorDebugFunction::GetModule 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
ms.openlocfilehash: e49bf6a7db9edb9e5ae489cc0655eea54406643d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137884"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="b742e-102">ICorDebugFunction::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="b742e-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="b742e-103">获取在其中定义此函数的模块。</span><span class="sxs-lookup"><span data-stu-id="b742e-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b742e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b742e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b742e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b742e-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="b742e-106">弄指向 ICorDebugModule 对象的地址的指针，该对象表示在其中定义此函数的模块。</span><span class="sxs-lookup"><span data-stu-id="b742e-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b742e-107">要求</span><span class="sxs-lookup"><span data-stu-id="b742e-107">Requirements</span></span>  
 <span data-ttu-id="b742e-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b742e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b742e-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b742e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b742e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b742e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b742e-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b742e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
