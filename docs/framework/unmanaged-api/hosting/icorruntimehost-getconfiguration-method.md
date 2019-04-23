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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf74da6eb0e7ce0215023a9a58d6b88c57c4fe8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097326"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="8021f-102">ICorRuntimeHost::GetConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="8021f-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="8021f-103">获取允许指定公共语言运行时 (CLR) 的回调配置主机的对象。</span><span class="sxs-lookup"><span data-stu-id="8021f-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8021f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8021f-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8021f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8021f-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="8021f-106">[out]指向的地址的指针[ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)可以用于配置 CLR 对象。</span><span class="sxs-lookup"><span data-stu-id="8021f-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8021f-107">备注</span><span class="sxs-lookup"><span data-stu-id="8021f-107">Remarks</span></span>  
 <span data-ttu-id="8021f-108">CLR 必须在其初始化; 之前配置否则为`GetConfiguration`方法返回一个 HRESULT，指示错误。</span><span class="sxs-lookup"><span data-stu-id="8021f-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8021f-109">要求</span><span class="sxs-lookup"><span data-stu-id="8021f-109">Requirements</span></span>  
 <span data-ttu-id="8021f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8021f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8021f-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8021f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8021f-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8021f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8021f-113">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8021f-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8021f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8021f-114">See also</span></span>

- [<span data-ttu-id="8021f-115">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="8021f-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
