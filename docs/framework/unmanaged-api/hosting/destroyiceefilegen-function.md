---
title: DestroyICeeFileGen 函数
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ba438fbd20bc2fdf8014005dc352f4610657cd9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558509"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="2b866-102">DestroyICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="2b866-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="2b866-103">销毁[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="2b866-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="2b866-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2b866-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b866-105">语法</span><span class="sxs-lookup"><span data-stu-id="2b866-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b866-106">参数</span><span class="sxs-lookup"><span data-stu-id="2b866-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="2b866-107">[in]`ICeeFileGen`要销毁对象。</span><span class="sxs-lookup"><span data-stu-id="2b866-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b866-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2b866-108">Return Value</span></span>  
 <span data-ttu-id="2b866-109">此方法返回标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="2b866-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b866-110">备注</span><span class="sxs-lookup"><span data-stu-id="2b866-110">Remarks</span></span>  
 <span data-ttu-id="2b866-111">`DestroyICeeFileGen` 销毁`ICeeFileGen`对象创建[CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2b866-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b866-112">要求</span><span class="sxs-lookup"><span data-stu-id="2b866-112">Requirements</span></span>  
 <span data-ttu-id="2b866-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b866-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b866-114">**标头：** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="2b866-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="2b866-115">**库：** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="2b866-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="2b866-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b866-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b866-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b866-117">See also</span></span>
- [<span data-ttu-id="2b866-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="2b866-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
