---
title: "AXL_AUTHENTICODE_SIGNER_INFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c53ca8073adda5cba497e9f45404024435cc161f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="722b0-102">AXL_AUTHENTICODE_SIGNER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="722b0-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="722b0-103">定义验证码签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="722b0-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="722b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="722b0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="722b0-105">成员</span><span class="sxs-lookup"><span data-stu-id="722b0-105">Members</span></span>  
  
|<span data-ttu-id="722b0-106">成员</span><span class="sxs-lookup"><span data-stu-id="722b0-106">Member</span></span>|<span data-ttu-id="722b0-107">描述</span><span class="sxs-lookup"><span data-stu-id="722b0-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="722b0-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="722b0-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="722b0-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="722b0-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="722b0-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="722b0-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="722b0-111">哈希。</span><span class="sxs-lookup"><span data-stu-id="722b0-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="722b0-112">说明。</span><span class="sxs-lookup"><span data-stu-id="722b0-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="722b0-113">说明的 URL。</span><span class="sxs-lookup"><span data-stu-id="722b0-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="722b0-114">签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="722b0-114">The chain context of the signer.</span></span> <span data-ttu-id="722b0-115">请参阅[CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="722b0-115">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="722b0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="722b0-116">See Also</span></span>  
 [<span data-ttu-id="722b0-117">验证码</span><span class="sxs-lookup"><span data-stu-id="722b0-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
