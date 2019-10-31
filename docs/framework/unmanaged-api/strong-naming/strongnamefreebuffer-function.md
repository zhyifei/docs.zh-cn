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
ms.openlocfilehash: 11821acbeeb04ae09464eb0e032b9bf387914168
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095053"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="bb9b3-102">StrongNameFreeBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="bb9b3-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="bb9b3-103">释放先前调用 [StrongNameGetPublicKey](strongnamegetpublickey-function.md)、[StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 或 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) 强名称函数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="bb9b3-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="bb9b3-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="bb9b3-104">This function has been deprecated.</span></span> <span data-ttu-id="bb9b3-105">改为使用[ICLRStrongName：： StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bb9b3-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb9b3-106">语法</span><span class="sxs-lookup"><span data-stu-id="bb9b3-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb9b3-107">参数</span><span class="sxs-lookup"><span data-stu-id="bb9b3-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="bb9b3-108">中指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="bb9b3-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb9b3-109">要求</span><span class="sxs-lookup"><span data-stu-id="bb9b3-109">Requirements</span></span>  
 <span data-ttu-id="bb9b3-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb9b3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb9b3-111">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="bb9b3-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bb9b3-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="bb9b3-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb9b3-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9b3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb9b3-114">See also</span></span>

- [<span data-ttu-id="bb9b3-115">StrongNameFreeBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="bb9b3-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="bb9b3-116">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="bb9b3-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
