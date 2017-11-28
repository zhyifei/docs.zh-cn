---
title: "DestroyICeeFileGen 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type: COM
f1_keywords: DestroyICeeFileGen
helpviewer_keywords: DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11f0bd03532668196f85713459fe103f9120c82e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="910e3-102">DestroyICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="910e3-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="910e3-103">销毁[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="910e3-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="910e3-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="910e3-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="910e3-105">语法</span><span class="sxs-lookup"><span data-stu-id="910e3-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="910e3-106">参数</span><span class="sxs-lookup"><span data-stu-id="910e3-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="910e3-107">[in]`ICeeFileGen`要销毁对象。</span><span class="sxs-lookup"><span data-stu-id="910e3-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="910e3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="910e3-108">Return Value</span></span>  
 <span data-ttu-id="910e3-109">此方法返回标准的 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="910e3-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="910e3-110">备注</span><span class="sxs-lookup"><span data-stu-id="910e3-110">Remarks</span></span>  
 <span data-ttu-id="910e3-111">`DestroyICeeFileGen`销毁`ICeeFileGen`创建对象[CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="910e3-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="910e3-112">要求</span><span class="sxs-lookup"><span data-stu-id="910e3-112">Requirements</span></span>  
 <span data-ttu-id="910e3-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="910e3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="910e3-114">**标头：** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="910e3-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="910e3-115">**库：** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="910e3-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="910e3-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="910e3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910e3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="910e3-117">See Also</span></span>  
 [<span data-ttu-id="910e3-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="910e3-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
