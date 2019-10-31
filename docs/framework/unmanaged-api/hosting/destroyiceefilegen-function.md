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
ms.openlocfilehash: 4eb878b61b72378bc6870af7f2cd09f0b6943b13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136505"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="1ab3f-102">DestroyICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="1ab3f-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="1ab3f-103">销毁[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="1ab3f-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="1ab3f-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="1ab3f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab3f-105">语法</span><span class="sxs-lookup"><span data-stu-id="1ab3f-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ab3f-106">参数</span><span class="sxs-lookup"><span data-stu-id="1ab3f-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="1ab3f-107">中要销毁的 `ICeeFileGen` 对象。</span><span class="sxs-lookup"><span data-stu-id="1ab3f-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ab3f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1ab3f-108">Return Value</span></span>  
 <span data-ttu-id="1ab3f-109">此方法返回标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="1ab3f-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab3f-110">备注</span><span class="sxs-lookup"><span data-stu-id="1ab3f-110">Remarks</span></span>  
 <span data-ttu-id="1ab3f-111">`DestroyICeeFileGen` 销毁[CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)函数创建的 `ICeeFileGen` 对象。</span><span class="sxs-lookup"><span data-stu-id="1ab3f-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ab3f-112">要求</span><span class="sxs-lookup"><span data-stu-id="1ab3f-112">Requirements</span></span>  
 <span data-ttu-id="1ab3f-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ab3f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab3f-114">**标头：** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="1ab3f-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="1ab3f-115">**库：** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="1ab3f-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="1ab3f-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab3f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab3f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ab3f-117">See also</span></span>

- [<span data-ttu-id="1ab3f-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="1ab3f-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
