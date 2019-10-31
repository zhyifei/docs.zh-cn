---
title: ICorDebugFrame::GetFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 39175e338e4fd98dd4af1325138da732ed81c764
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137925"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="a308b-102">ICorDebugFrame::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="a308b-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="a308b-103">获取一个函数，该函数包含与此堆栈帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="a308b-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a308b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a308b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a308b-105">参数</span><span class="sxs-lookup"><span data-stu-id="a308b-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="a308b-106">弄指向 ICorDebugFunction 对象的地址的指针，该对象表示包含与此堆栈帧关联的代码的函数。</span><span class="sxs-lookup"><span data-stu-id="a308b-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a308b-107">备注</span><span class="sxs-lookup"><span data-stu-id="a308b-107">Remarks</span></span>  
 <span data-ttu-id="a308b-108">如果框架不与任何特定函数相关联，则 `GetFunction` 方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="a308b-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a308b-109">要求</span><span class="sxs-lookup"><span data-stu-id="a308b-109">Requirements</span></span>  
 <span data-ttu-id="a308b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a308b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a308b-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a308b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a308b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a308b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a308b-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a308b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
