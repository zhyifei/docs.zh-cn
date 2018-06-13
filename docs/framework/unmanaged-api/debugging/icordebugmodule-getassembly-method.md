---
title: ICorDebugModule::GetAssembly 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78bfc91bdd0f9fa68252c6a07e1362807eb507b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416018"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="30b4a-102">ICorDebugModule::GetAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="30b4a-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="30b4a-103">获取此模块包含程序集。</span><span class="sxs-lookup"><span data-stu-id="30b4a-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b4a-104">语法</span><span class="sxs-lookup"><span data-stu-id="30b4a-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30b4a-105">参数</span><span class="sxs-lookup"><span data-stu-id="30b4a-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="30b4a-106">[out]指向一个表示包含此模块的程序集的 icor 调试程序集对象的指针。</span><span class="sxs-lookup"><span data-stu-id="30b4a-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30b4a-107">要求</span><span class="sxs-lookup"><span data-stu-id="30b4a-107">Requirements</span></span>  
 <span data-ttu-id="30b4a-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30b4a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30b4a-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30b4a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30b4a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30b4a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30b4a-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30b4a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
