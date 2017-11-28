---
title: "ICLRStrongName2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName2
helpviewer_keywords: ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9e9a88f1064c888d60e363be569d06458299143d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="0aa09-102">ICLRStrongName2 接口</span><span class="sxs-lookup"><span data-stu-id="0aa09-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="0aa09-103">提供创建使用安全哈希算法 （sha-256、 sha-384 和 sha-512） 的 sha-2 组的强名称的能力。</span><span class="sxs-lookup"><span data-stu-id="0aa09-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0aa09-104">方法</span><span class="sxs-lookup"><span data-stu-id="0aa09-104">Methods</span></span>  
  
|<span data-ttu-id="0aa09-105">方法</span><span class="sxs-lookup"><span data-stu-id="0aa09-105">Method</span></span>|<span data-ttu-id="0aa09-106">描述</span><span class="sxs-lookup"><span data-stu-id="0aa09-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0aa09-107">StrongNameGetPublicKeyEx 方法</span><span class="sxs-lookup"><span data-stu-id="0aa09-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="0aa09-108">公钥/私钥对，从获取的公共密钥，并指定哈希算法和签名算法。</span><span class="sxs-lookup"><span data-stu-id="0aa09-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="0aa09-109">StrongNameSignatureVerificationEx2 方法</span><span class="sxs-lookup"><span data-stu-id="0aa09-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="0aa09-110">验证强名称程序集签名，并提供从 ECMA 键到真实键的映射。</span><span class="sxs-lookup"><span data-stu-id="0aa09-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aa09-111">备注</span><span class="sxs-lookup"><span data-stu-id="0aa09-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aa09-112">要求</span><span class="sxs-lookup"><span data-stu-id="0aa09-112">Requirements</span></span>  
 <span data-ttu-id="0aa09-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa09-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aa09-114">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0aa09-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0aa09-115">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0aa09-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0aa09-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aa09-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
