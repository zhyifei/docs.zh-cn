---
title: ITypeNameFactory::ParseTypeName 方法
ms.date: 03/30/2017
api_name:
- ITypeNameFactory.ParseTypeName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ParseTypeName
helpviewer_keywords:
- ITypeNameFactory::ParseTypeName method [.NET Framework hosting]
- ParseTypeName method [.NET Framework hosting]
ms.assetid: 13c9f063-371c-4911-a5e7-e1e0b88ae382
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe5f634a5d0580c7e58b03f318da98a0112fa6b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208080"
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="345b1-102">ITypeNameFactory::ParseTypeName 方法</span><span class="sxs-lookup"><span data-stu-id="345b1-102">ITypeNameFactory::ParseTypeName Method</span></span>
<span data-ttu-id="345b1-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="345b1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="345b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="345b1-104">Syntax</span></span>  
  
```  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="345b1-105">要求</span><span class="sxs-lookup"><span data-stu-id="345b1-105">Requirements</span></span>  
 <span data-ttu-id="345b1-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="345b1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="345b1-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="345b1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="345b1-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="345b1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="345b1-109">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="345b1-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="345b1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="345b1-110">See also</span></span>

- [<span data-ttu-id="345b1-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="345b1-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
