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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aef12634da477e72757e98e520b600ec1ee0f1b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412160"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="3ab8e-102">ICorDebugFunction::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="3ab8e-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="3ab8e-103">获取在其中定义此函数的模块。</span><span class="sxs-lookup"><span data-stu-id="3ab8e-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ab8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ab8e-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ab8e-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ab8e-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="3ab8e-106">[out]指向一个表示在其中定义此函数的模块的 icor 调试模块对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3ab8e-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ab8e-107">要求</span><span class="sxs-lookup"><span data-stu-id="3ab8e-107">Requirements</span></span>  
 <span data-ttu-id="3ab8e-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ab8e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ab8e-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ab8e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ab8e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ab8e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ab8e-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ab8e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
