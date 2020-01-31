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
ms.openlocfilehash: 35e3e37b1487b5dda9945402c6a3338384147f9a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792629"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="e4a1a-102">ICorDebugProcess::EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="e4a1a-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="e4a1a-103">枚举此进程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e4a1a-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a1a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4a1a-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4a1a-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4a1a-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="e4a1a-106">弄一个指针，指向[ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)的地址，该地址是此进程中的应用程序域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="e4a1a-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4a1a-107">备注</span><span class="sxs-lookup"><span data-stu-id="e4a1a-107">Remarks</span></span>  
 <span data-ttu-id="e4a1a-108">此方法可在[ICorDebugManagedCallback：： CreateProcess](icordebugmanagedcallback-createprocess-method.md)回调之前使用。</span><span class="sxs-lookup"><span data-stu-id="e4a1a-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4a1a-109">需求</span><span class="sxs-lookup"><span data-stu-id="e4a1a-109">Requirements</span></span>  
 <span data-ttu-id="e4a1a-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a1a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4a1a-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4a1a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4a1a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4a1a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4a1a-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4a1a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
