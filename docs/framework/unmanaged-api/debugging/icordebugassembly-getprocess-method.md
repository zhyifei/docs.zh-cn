---
title: ICorDebugAssembly::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeadcbd8f2d09320645c36fdc771cfb2cb976036
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471246"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="c32bc-102">ICorDebugAssembly::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="c32bc-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="c32bc-103">获取在其中运行此 icor 调试程序集实例的进程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="c32bc-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c32bc-104">语法</span><span class="sxs-lookup"><span data-stu-id="c32bc-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c32bc-105">参数</span><span class="sxs-lookup"><span data-stu-id="c32bc-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="c32bc-106">[out]指向表示流程 ICorDebugProcess 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="c32bc-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c32bc-107">要求</span><span class="sxs-lookup"><span data-stu-id="c32bc-107">Requirements</span></span>  
 <span data-ttu-id="c32bc-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c32bc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c32bc-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c32bc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c32bc-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c32bc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c32bc-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c32bc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
