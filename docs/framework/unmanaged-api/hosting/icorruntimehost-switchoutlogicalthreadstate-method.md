---
title: ICorRuntimeHost::SwitchOutLogicalThreadState 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
ms.openlocfilehash: f32381dc40a744157e46780e59b83efd63e58dcb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762638"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="eef83-102">ICorRuntimeHost::SwitchOutLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="eef83-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="eef83-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="eef83-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef83-104">语法</span><span class="sxs-lookup"><span data-stu-id="eef83-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eef83-105">参数</span><span class="sxs-lookup"><span data-stu-id="eef83-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="eef83-106">弄指示要交换的纤程的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="eef83-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eef83-107">要求</span><span class="sxs-lookup"><span data-stu-id="eef83-107">Requirements</span></span>  
 <span data-ttu-id="eef83-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eef83-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eef83-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="eef83-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eef83-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="eef83-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eef83-111">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="eef83-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef83-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eef83-112">See also</span></span>

- [<span data-ttu-id="eef83-113">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="eef83-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
