---
title: ICorDebugProcess::EnumerateAppDomains 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: 4489238df05edef384b4073ee738a184ff8809ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178677"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="f6cd1-102">ICorDebugProcess::EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="f6cd1-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="f6cd1-103">枚举在此过程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f6cd1-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6cd1-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6cd1-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6cd1-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f6cd1-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="f6cd1-106">[出]指向[ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)地址的指针，该地址是在此过程中应用程序域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="f6cd1-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6cd1-107">备注</span><span class="sxs-lookup"><span data-stu-id="f6cd1-107">Remarks</span></span>  
 <span data-ttu-id="f6cd1-108">此方法可以在[ICorDebug 托管回调之前使用：创建进程](icordebugmanagedcallback-createprocess-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="f6cd1-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6cd1-109">要求</span><span class="sxs-lookup"><span data-stu-id="f6cd1-109">Requirements</span></span>  
 <span data-ttu-id="f6cd1-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6cd1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6cd1-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6cd1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6cd1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6cd1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6cd1-113">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6cd1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
