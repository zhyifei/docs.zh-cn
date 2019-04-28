---
title: ICLRStrongName2 接口
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf9e3d2df8f507e118b393007c3958358a830cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763719"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="8f9e3-102">ICLRStrongName2 接口</span><span class="sxs-lookup"><span data-stu-id="8f9e3-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="8f9e3-103">提供的功能来创建强名称使用 SHA-2 组的安全哈希算法 （SHA-256、 SHA-384 和 SHA-512）。</span><span class="sxs-lookup"><span data-stu-id="8f9e3-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f9e3-104">方法</span><span class="sxs-lookup"><span data-stu-id="8f9e3-104">Methods</span></span>  
  
|<span data-ttu-id="8f9e3-105">方法</span><span class="sxs-lookup"><span data-stu-id="8f9e3-105">Method</span></span>|<span data-ttu-id="8f9e3-106">描述</span><span class="sxs-lookup"><span data-stu-id="8f9e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f9e3-107">StrongNameGetPublicKeyEx 方法</span><span class="sxs-lookup"><span data-stu-id="8f9e3-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="8f9e3-108">从公钥/私钥对，获取的公钥，并指定哈希算法和签名算法。</span><span class="sxs-lookup"><span data-stu-id="8f9e3-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="8f9e3-109">StrongNameSignatureVerificationEx2 方法</span><span class="sxs-lookup"><span data-stu-id="8f9e3-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="8f9e3-110">签名验证证书的强名称程序集，并提供从 ECMA 键到真实键的映射。</span><span class="sxs-lookup"><span data-stu-id="8f9e3-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f9e3-111">备注</span><span class="sxs-lookup"><span data-stu-id="8f9e3-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f9e3-112">要求</span><span class="sxs-lookup"><span data-stu-id="8f9e3-112">Requirements</span></span>  
 <span data-ttu-id="8f9e3-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f9e3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f9e3-114">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8f9e3-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8f9e3-115">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8f9e3-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f9e3-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f9e3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
