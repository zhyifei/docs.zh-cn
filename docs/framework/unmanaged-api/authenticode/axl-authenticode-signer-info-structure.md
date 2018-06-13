---
title: AXL_AUTHENTICODE_SIGNER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd07707b5a80ec0980fc50b27caddf0a24398fd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400440"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="90d1f-102">AXL_AUTHENTICODE_SIGNER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="90d1f-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="90d1f-103">定义验证码签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="90d1f-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90d1f-104">语法</span><span class="sxs-lookup"><span data-stu-id="90d1f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="90d1f-105">成员</span><span class="sxs-lookup"><span data-stu-id="90d1f-105">Members</span></span>  
  
|<span data-ttu-id="90d1f-106">成员</span><span class="sxs-lookup"><span data-stu-id="90d1f-106">Member</span></span>|<span data-ttu-id="90d1f-107">描述</span><span class="sxs-lookup"><span data-stu-id="90d1f-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="90d1f-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="90d1f-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="90d1f-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="90d1f-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="90d1f-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="90d1f-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="90d1f-111">哈希。</span><span class="sxs-lookup"><span data-stu-id="90d1f-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="90d1f-112">说明。</span><span class="sxs-lookup"><span data-stu-id="90d1f-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="90d1f-113">说明的 URL。</span><span class="sxs-lookup"><span data-stu-id="90d1f-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="90d1f-114">签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="90d1f-114">The chain context of the signer.</span></span> <span data-ttu-id="90d1f-115">请参阅[CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="90d1f-115">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90d1f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="90d1f-116">See Also</span></span>  
 [<span data-ttu-id="90d1f-117">验证码</span><span class="sxs-lookup"><span data-stu-id="90d1f-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
