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
ms.openlocfilehash: d1c3bcc0ed22fa970d92e2384277d0786016db19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="e6c40-102">ICorDebugAssembly::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="e6c40-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="e6c40-103">获取在其中运行此 icor 调试程序集实例的进程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="e6c40-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6c40-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6c40-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6c40-105">参数</span><span class="sxs-lookup"><span data-stu-id="e6c40-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="e6c40-106">[out]表示进程的 ICorDebugProcess 接口指针。</span><span class="sxs-lookup"><span data-stu-id="e6c40-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6c40-107">要求</span><span class="sxs-lookup"><span data-stu-id="e6c40-107">Requirements</span></span>  
 <span data-ttu-id="e6c40-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6c40-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6c40-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6c40-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6c40-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6c40-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6c40-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6c40-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
