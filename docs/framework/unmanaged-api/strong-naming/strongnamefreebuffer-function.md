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
ms.openlocfilehash: 639664c6ce5714b554f30bff2569a12bf48d1671
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799121"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="8aeab-102">StrongNameFreeBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="8aeab-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="8aeab-103">释放先前调用 [StrongNameGetPublicKey](strongnamegetpublickey-function.md)、[StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 或 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) 强名称函数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="8aeab-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="8aeab-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="8aeab-104">This function has been deprecated.</span></span> <span data-ttu-id="8aeab-105">改为使用[ICLRStrongName：： StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8aeab-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aeab-106">语法</span><span class="sxs-lookup"><span data-stu-id="8aeab-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8aeab-107">参数</span><span class="sxs-lookup"><span data-stu-id="8aeab-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="8aeab-108">中指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="8aeab-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aeab-109">要求</span><span class="sxs-lookup"><span data-stu-id="8aeab-109">Requirements</span></span>  
 <span data-ttu-id="8aeab-110">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8aeab-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aeab-111">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="8aeab-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8aeab-112">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8aeab-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8aeab-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aeab-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aeab-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8aeab-114">See also</span></span>

- [<span data-ttu-id="8aeab-115">StrongNameFreeBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="8aeab-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="8aeab-116">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="8aeab-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
