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
ms.openlocfilehash: 57f771d933e896677dfc0bd5d9dac58da2af22c8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617251"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="deb47-102">GetCLRIdentityManager 函数</span><span class="sxs-lookup"><span data-stu-id="deb47-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="deb47-103">获取一个指向接口的指针，该接口允许公共语言运行时（CLR）管理标识。</span><span class="sxs-lookup"><span data-stu-id="deb47-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="deb47-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="deb47-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb47-105">语法</span><span class="sxs-lookup"><span data-stu-id="deb47-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="deb47-106">参数</span><span class="sxs-lookup"><span data-stu-id="deb47-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="deb47-107">中一个 `REFIID` （接口标识符），它指定要获取的接口。</span><span class="sxs-lookup"><span data-stu-id="deb47-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="deb47-108">此值必须是 IID_ICLRAssemblyIdentityManager 或 IID_ICLRHostBindingPolicyManager。</span><span class="sxs-lookup"><span data-stu-id="deb47-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="deb47-109">弄指向[ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)或[ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="deb47-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="deb47-110">备注</span><span class="sxs-lookup"><span data-stu-id="deb47-110">Remarks</span></span>  
 <span data-ttu-id="deb47-111">调用[GetRealProcAddress](getrealprocaddress-function.md)函数以获取指向函数的指针 `GetCLRIdentityManager` 。</span><span class="sxs-lookup"><span data-stu-id="deb47-111">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deb47-112">要求</span><span class="sxs-lookup"><span data-stu-id="deb47-112">Requirements</span></span>  
 <span data-ttu-id="deb47-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="deb47-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb47-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="deb47-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="deb47-115">**库：** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="deb47-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="deb47-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb47-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb47-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="deb47-117">See also</span></span>

- [<span data-ttu-id="deb47-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="deb47-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
