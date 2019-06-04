---
title: GetCLRIdentityManager 函数
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e18172ecf2d4300ae42cc42ecdb1783744cac105
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490417"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="4b321-102">GetCLRIdentityManager 函数</span><span class="sxs-lookup"><span data-stu-id="4b321-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="4b321-103">获取一个指针指向使公共语言运行时 (CLR) 来管理标识的接口。</span><span class="sxs-lookup"><span data-stu-id="4b321-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="4b321-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="4b321-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b321-105">语法</span><span class="sxs-lookup"><span data-stu-id="4b321-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b321-106">参数</span><span class="sxs-lookup"><span data-stu-id="4b321-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="4b321-107">[in]一个`REFIID`（接口标识符），它指定要获取的接口。</span><span class="sxs-lookup"><span data-stu-id="4b321-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="4b321-108">此值必须是 IID_ICLRAssemblyIdentityManager 或 IID_ICLRHostBindingPolicyManager。</span><span class="sxs-lookup"><span data-stu-id="4b321-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="4b321-109">[out]指向任何一个的地址的指针[ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)或[ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="4b321-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b321-110">备注</span><span class="sxs-lookup"><span data-stu-id="4b321-110">Remarks</span></span>  
 <span data-ttu-id="4b321-111">调用[GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)函数获取指向的`GetCLRIdentityManager`函数。</span><span class="sxs-lookup"><span data-stu-id="4b321-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b321-112">要求</span><span class="sxs-lookup"><span data-stu-id="4b321-112">Requirements</span></span>  
 <span data-ttu-id="4b321-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4b321-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b321-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b321-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b321-115">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="4b321-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="4b321-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b321-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b321-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b321-117">See also</span></span>

- [<span data-ttu-id="4b321-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="4b321-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
