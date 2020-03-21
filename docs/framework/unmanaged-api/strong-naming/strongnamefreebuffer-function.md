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
ms.openlocfilehash: 50e3cc6e677de45be9256a2a818ebd6ed7d8b843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176911"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="dec7b-102">StrongNameFreeBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="dec7b-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="dec7b-103">释放先前调用 [StrongNameGetPublicKey](strongnamegetpublickey-function.md)、[StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 或 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) 强名称函数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="dec7b-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="dec7b-104">此函数已被弃用。</span><span class="sxs-lookup"><span data-stu-id="dec7b-104">This function has been deprecated.</span></span> <span data-ttu-id="dec7b-105">改用[ICLR 强名称：：强名称自由缓冲区](../hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="dec7b-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec7b-106">语法</span><span class="sxs-lookup"><span data-stu-id="dec7b-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dec7b-107">parameters</span><span class="sxs-lookup"><span data-stu-id="dec7b-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="dec7b-108">[在]指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="dec7b-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dec7b-109">要求</span><span class="sxs-lookup"><span data-stu-id="dec7b-109">Requirements</span></span>  
 <span data-ttu-id="dec7b-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dec7b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dec7b-111">**标题：** 强名称.h</span><span class="sxs-lookup"><span data-stu-id="dec7b-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="dec7b-112">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="dec7b-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dec7b-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dec7b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec7b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dec7b-114">See also</span></span>

- [<span data-ttu-id="dec7b-115">StrongNameFreeBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="dec7b-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="dec7b-116">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="dec7b-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
