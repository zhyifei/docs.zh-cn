---
title: AXL_AUTHENTICODE_SIGNER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b9f54c7c57d122ac1214b9f31cc4e1d1cddd71c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43670527"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="43dc3-102">AXL_AUTHENTICODE_SIGNER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="43dc3-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="43dc3-103">定义验证码签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="43dc3-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43dc3-104">语法</span><span class="sxs-lookup"><span data-stu-id="43dc3-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="43dc3-105">成员</span><span class="sxs-lookup"><span data-stu-id="43dc3-105">Members</span></span>  
  
|<span data-ttu-id="43dc3-106">成员</span><span class="sxs-lookup"><span data-stu-id="43dc3-106">Member</span></span>|<span data-ttu-id="43dc3-107">描述</span><span class="sxs-lookup"><span data-stu-id="43dc3-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="43dc3-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="43dc3-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="43dc3-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="43dc3-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="43dc3-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="43dc3-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="43dc3-111">哈希。</span><span class="sxs-lookup"><span data-stu-id="43dc3-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="43dc3-112">说明。</span><span class="sxs-lookup"><span data-stu-id="43dc3-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="43dc3-113">说明的 URL。</span><span class="sxs-lookup"><span data-stu-id="43dc3-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="43dc3-114">签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="43dc3-114">The chain context of the signer.</span></span> <span data-ttu-id="43dc3-115">请参阅[CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context)结构。</span><span class="sxs-lookup"><span data-stu-id="43dc3-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43dc3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="43dc3-116">See Also</span></span>  
 [<span data-ttu-id="43dc3-117">验证码</span><span class="sxs-lookup"><span data-stu-id="43dc3-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
