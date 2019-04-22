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
ms.openlocfilehash: 07deb2c1b7100362b7dbce41e25db53308de809c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159856"
---
# <a name="itypenamegettypeargumentcount-method"></a><span data-ttu-id="ca80a-102">ITypeName::GetTypeArgumentCount 方法</span><span class="sxs-lookup"><span data-stu-id="ca80a-102">ITypeName::GetTypeArgumentCount Method</span></span>
<span data-ttu-id="ca80a-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="ca80a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca80a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca80a-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArgumentCount (  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ca80a-105">要求</span><span class="sxs-lookup"><span data-stu-id="ca80a-105">Requirements</span></span>  
 <span data-ttu-id="ca80a-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca80a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca80a-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca80a-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca80a-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ca80a-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca80a-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca80a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca80a-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca80a-110">See also</span></span>

- [<span data-ttu-id="ca80a-111">承载接口</span><span class="sxs-lookup"><span data-stu-id="ca80a-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
