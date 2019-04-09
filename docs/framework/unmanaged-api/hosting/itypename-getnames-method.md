---
title: ITypeName::GetNames 方法
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28076a36880febad20d457ff5a6b290de3d6f173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121545"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="53b88-102">ITypeName::GetNames 方法</span><span class="sxs-lookup"><span data-stu-id="53b88-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="53b88-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="53b88-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b88-104">语法</span><span class="sxs-lookup"><span data-stu-id="53b88-104">Syntax</span></span>  
  
```  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="53b88-105">要求</span><span class="sxs-lookup"><span data-stu-id="53b88-105">Requirements</span></span>  
 <span data-ttu-id="53b88-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53b88-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53b88-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="53b88-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53b88-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="53b88-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="53b88-109">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="53b88-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53b88-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="53b88-110">See also</span></span>

- [<span data-ttu-id="53b88-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="53b88-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
