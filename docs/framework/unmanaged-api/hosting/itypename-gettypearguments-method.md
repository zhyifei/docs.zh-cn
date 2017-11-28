---
title: "ITypeName::GetTypeArguments 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ITypeName.GetTypeArguments
api_location: mscoree.dll
api_type: COM
f1_keywords: GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c580a6ff78668bdddda01f4892c6bb425bb2cab7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="cd862-102">ITypeName::GetTypeArguments 方法</span><span class="sxs-lookup"><span data-stu-id="cd862-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="cd862-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="cd862-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd862-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd862-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cd862-105">要求</span><span class="sxs-lookup"><span data-stu-id="cd862-105">Requirements</span></span>  
 <span data-ttu-id="cd862-106">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd862-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd862-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd862-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd862-108">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cd862-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd862-109">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd862-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd862-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd862-110">See Also</span></span>  
 [<span data-ttu-id="cd862-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="cd862-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
