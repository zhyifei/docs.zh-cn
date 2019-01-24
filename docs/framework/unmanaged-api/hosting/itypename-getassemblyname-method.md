---
title: ITypeName::GetAssemblyName 方法
ms.date: 03/30/2017
api_name:
- ITypeName.GetAssemblyName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetAssemblyName
helpviewer_keywords:
- ITypeName::GetAssemblyName method [.NET Framework hosting]
- GetAssemblyName method [.NET Framework hosting]
ms.assetid: 97801d99-f5f1-4a30-882f-959827093fac
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2bf61de20d619fb2c89cee0175e256f596ba9f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668023"
---
# <a name="itypenamegetassemblyname-method"></a><span data-ttu-id="3cffd-102">ITypeName::GetAssemblyName 方法</span><span class="sxs-lookup"><span data-stu-id="3cffd-102">ITypeName::GetAssemblyName Method</span></span>
<span data-ttu-id="3cffd-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="3cffd-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cffd-104">语法</span><span class="sxs-lookup"><span data-stu-id="3cffd-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyName (  
    [out, retval] BSTR* rgbszAssemblyNames  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3cffd-105">要求</span><span class="sxs-lookup"><span data-stu-id="3cffd-105">Requirements</span></span>  
 <span data-ttu-id="3cffd-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3cffd-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cffd-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3cffd-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cffd-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3cffd-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cffd-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cffd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cffd-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cffd-110">See also</span></span>
- [<span data-ttu-id="3cffd-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="3cffd-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
