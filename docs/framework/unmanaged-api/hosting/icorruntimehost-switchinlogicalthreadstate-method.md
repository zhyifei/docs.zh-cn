---
title: ICorRuntimeHost::SwitchInLogicalThreadState 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: b6569b5dab89a88a24cf2dfc873da9740e5af505
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133382"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="81833-102">ICorRuntimeHost::SwitchInLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="81833-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="81833-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="81833-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81833-104">语法</span><span class="sxs-lookup"><span data-stu-id="81833-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81833-105">参数</span><span class="sxs-lookup"><span data-stu-id="81833-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="81833-106">中指示要使用的纤程的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="81833-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81833-107">要求</span><span class="sxs-lookup"><span data-stu-id="81833-107">Requirements</span></span>  
 <span data-ttu-id="81833-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81833-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81833-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="81833-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81833-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="81833-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81833-111">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="81833-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81833-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="81833-112">See also</span></span>

- [<span data-ttu-id="81833-113">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="81833-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
