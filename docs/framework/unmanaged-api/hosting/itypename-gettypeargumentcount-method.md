---
title: ITypeName::GetTypeArgumentCount 方法
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArgumentCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArgumentCount
helpviewer_keywords:
- GetTypeArgumentCount method [.NET Framework hosting]
- ITypeName::GetTypeArgumentCount method [.NET Framework hosting]
ms.assetid: ecb5480c-761a-4b02-83e0-b79abc67fd08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88c2818bd3ad86e7683ffbe6c5454fca560dacde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757736"
---
# <a name="itypenamegettypeargumentcount-method"></a><span data-ttu-id="cd41e-102">ITypeName::GetTypeArgumentCount 方法</span><span class="sxs-lookup"><span data-stu-id="cd41e-102">ITypeName::GetTypeArgumentCount Method</span></span>
<span data-ttu-id="cd41e-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="cd41e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd41e-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd41e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArgumentCount (  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cd41e-105">要求</span><span class="sxs-lookup"><span data-stu-id="cd41e-105">Requirements</span></span>  
 <span data-ttu-id="cd41e-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd41e-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd41e-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd41e-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd41e-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cd41e-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd41e-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd41e-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd41e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd41e-110">See also</span></span>

- [<span data-ttu-id="cd41e-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="cd41e-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
