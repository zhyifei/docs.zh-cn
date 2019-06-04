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
ms.openlocfilehash: daf674c0340998c0fd518e0f1af721bbe9ff653c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490467"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="82610-102">DestroyICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="82610-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="82610-103">销毁[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="82610-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="82610-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="82610-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82610-105">语法</span><span class="sxs-lookup"><span data-stu-id="82610-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82610-106">参数</span><span class="sxs-lookup"><span data-stu-id="82610-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="82610-107">[in]`ICeeFileGen`要销毁对象。</span><span class="sxs-lookup"><span data-stu-id="82610-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82610-108">返回值</span><span class="sxs-lookup"><span data-stu-id="82610-108">Return Value</span></span>  
 <span data-ttu-id="82610-109">此方法返回标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="82610-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82610-110">备注</span><span class="sxs-lookup"><span data-stu-id="82610-110">Remarks</span></span>  
 <span data-ttu-id="82610-111">`DestroyICeeFileGen` 销毁`ICeeFileGen`对象创建[CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="82610-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82610-112">要求</span><span class="sxs-lookup"><span data-stu-id="82610-112">Requirements</span></span>  
 <span data-ttu-id="82610-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82610-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82610-114">**标头：** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="82610-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="82610-115">**库：** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="82610-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="82610-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82610-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82610-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="82610-117">See also</span></span>

- [<span data-ttu-id="82610-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="82610-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
