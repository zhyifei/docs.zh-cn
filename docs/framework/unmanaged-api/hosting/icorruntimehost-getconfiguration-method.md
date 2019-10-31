---
title: ICorRuntimeHost::GetConfiguration 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 87549118742da797ef0dd1b08ae9e72c466f7841
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139576"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="aed2b-102">ICorRuntimeHost::GetConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="aed2b-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="aed2b-103">获取一个对象，该对象允许宿主指定公共语言运行时（CLR）的回调配置。</span><span class="sxs-lookup"><span data-stu-id="aed2b-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aed2b-104">语法</span><span class="sxs-lookup"><span data-stu-id="aed2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aed2b-105">参数</span><span class="sxs-lookup"><span data-stu-id="aed2b-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="aed2b-106">弄指向可用于配置 CLR 的[ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="aed2b-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aed2b-107">备注</span><span class="sxs-lookup"><span data-stu-id="aed2b-107">Remarks</span></span>  
 <span data-ttu-id="aed2b-108">必须在初始化之前配置 CLR;否则，`GetConfiguration` 方法返回一个 HRESULT，指示错误。</span><span class="sxs-lookup"><span data-stu-id="aed2b-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aed2b-109">要求</span><span class="sxs-lookup"><span data-stu-id="aed2b-109">Requirements</span></span>  
 <span data-ttu-id="aed2b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aed2b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aed2b-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aed2b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aed2b-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="aed2b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aed2b-113">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="aed2b-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed2b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="aed2b-114">See also</span></span>

- [<span data-ttu-id="aed2b-115">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="aed2b-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
