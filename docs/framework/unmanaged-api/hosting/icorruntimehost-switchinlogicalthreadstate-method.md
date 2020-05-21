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
ms.openlocfilehash: d830635b911fa5d80382e432f283c455c41af7a8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762677"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="33c7a-102">ICorRuntimeHost::SwitchInLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="33c7a-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="33c7a-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="33c7a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33c7a-104">语法</span><span class="sxs-lookup"><span data-stu-id="33c7a-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33c7a-105">参数</span><span class="sxs-lookup"><span data-stu-id="33c7a-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="33c7a-106">中指示要使用的纤程的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="33c7a-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33c7a-107">要求</span><span class="sxs-lookup"><span data-stu-id="33c7a-107">Requirements</span></span>  
 <span data-ttu-id="33c7a-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33c7a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33c7a-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="33c7a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33c7a-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="33c7a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33c7a-111">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="33c7a-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c7a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33c7a-112">See also</span></span>

- [<span data-ttu-id="33c7a-113">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="33c7a-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
