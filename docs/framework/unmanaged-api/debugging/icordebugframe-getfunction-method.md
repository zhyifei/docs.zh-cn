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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b622d1bd82e53d5fa232e07b1f49e6fbba3ccba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414825"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="f95a7-102">ICorDebugFrame::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="f95a7-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="f95a7-103">获取包含与此堆栈帧关联的代码的函数。</span><span class="sxs-lookup"><span data-stu-id="f95a7-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f95a7-104">语法</span><span class="sxs-lookup"><span data-stu-id="f95a7-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f95a7-105">参数</span><span class="sxs-lookup"><span data-stu-id="f95a7-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="f95a7-106">[out]指向一个 ICorDebugFunction 对象，表示包含与此堆栈帧关联的代码的函数的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f95a7-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f95a7-107">备注</span><span class="sxs-lookup"><span data-stu-id="f95a7-107">Remarks</span></span>  
 <span data-ttu-id="f95a7-108">`GetFunction`方法如果帧不是与任何特定函数可能会失败。</span><span class="sxs-lookup"><span data-stu-id="f95a7-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f95a7-109">要求</span><span class="sxs-lookup"><span data-stu-id="f95a7-109">Requirements</span></span>  
 <span data-ttu-id="f95a7-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f95a7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f95a7-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f95a7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f95a7-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f95a7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f95a7-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f95a7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
