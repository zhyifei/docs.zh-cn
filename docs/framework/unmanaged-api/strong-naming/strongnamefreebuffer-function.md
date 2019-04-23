---
title: StrongNameFreeBuffer 函数
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bfc6491a1d18c81a44a7d9c5084f744c9b76281
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072567"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="1766c-102">StrongNameFreeBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="1766c-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="1766c-103">释放先前调用 [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)、[StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) 或 [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md) 强名称函数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="1766c-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="1766c-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="1766c-104">This function has been deprecated.</span></span> <span data-ttu-id="1766c-105">使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="1766c-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1766c-106">语法</span><span class="sxs-lookup"><span data-stu-id="1766c-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1766c-107">参数</span><span class="sxs-lookup"><span data-stu-id="1766c-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="1766c-108">[in]指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="1766c-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1766c-109">要求</span><span class="sxs-lookup"><span data-stu-id="1766c-109">Requirements</span></span>  
 <span data-ttu-id="1766c-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1766c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1766c-111">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1766c-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1766c-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1766c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1766c-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1766c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1766c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1766c-114">See also</span></span>

- [<span data-ttu-id="1766c-115">StrongNameFreeBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="1766c-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="1766c-116">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="1766c-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
