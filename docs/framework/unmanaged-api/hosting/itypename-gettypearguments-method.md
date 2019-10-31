---
title: ITypeName::GetTypeArguments 方法
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
ms.openlocfilehash: ac835459f88655377d96699e6aea0e877218c8fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125275"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="fa162-102">ITypeName::GetTypeArguments 方法</span><span class="sxs-lookup"><span data-stu-id="fa162-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="fa162-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="fa162-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa162-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa162-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="fa162-105">要求</span><span class="sxs-lookup"><span data-stu-id="fa162-105">Requirements</span></span>  
 <span data-ttu-id="fa162-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa162-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa162-107">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fa162-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa162-108">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fa162-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa162-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa162-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa162-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa162-110">See also</span></span>

- [<span data-ttu-id="fa162-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="fa162-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
