---
title: ICorDebugAssembly::GetAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fced656168952c1064de213405147baf7856b2c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737357"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="0ef5f-102">ICorDebugAssembly::GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="0ef5f-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="0ef5f-103">获取包含此应用程序域的接口指针`ICorDebugAssembly`实例。</span><span class="sxs-lookup"><span data-stu-id="0ef5f-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef5f-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ef5f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ef5f-105">参数</span><span class="sxs-lookup"><span data-stu-id="0ef5f-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="0ef5f-106">[out]指向表示应用程序域的 ICorDebugAppDomain 接口的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="0ef5f-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ef5f-107">备注</span><span class="sxs-lookup"><span data-stu-id="0ef5f-107">Remarks</span></span>  
 <span data-ttu-id="0ef5f-108">如果此程序集是系统程序集， `GetAppDomain` ，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="0ef5f-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ef5f-109">要求</span><span class="sxs-lookup"><span data-stu-id="0ef5f-109">Requirements</span></span>  
 <span data-ttu-id="0ef5f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ef5f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ef5f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ef5f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ef5f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ef5f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ef5f-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ef5f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
