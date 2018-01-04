---
title: "PublicKeyBlob 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PublicKeyBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: PublicKeyBlob
helpviewer_keywords: PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b70ab9ee04ff2a060f3c66173a3628032afc0b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="9a52e-102">PublicKeyBlob 结构</span><span class="sxs-lookup"><span data-stu-id="9a52e-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="9a52e-103">以二进制格式表示公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="9a52e-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a52e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9a52e-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="9a52e-105">成员</span><span class="sxs-lookup"><span data-stu-id="9a52e-105">Members</span></span>  
  
|<span data-ttu-id="9a52e-106">成员</span><span class="sxs-lookup"><span data-stu-id="9a52e-106">Member</span></span>|<span data-ttu-id="9a52e-107">描述</span><span class="sxs-lookup"><span data-stu-id="9a52e-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="9a52e-108">签名算法的标识符 (类型的`ALG_ID`，如 WinCrypt.h 中定义) 的公钥。</span><span class="sxs-lookup"><span data-stu-id="9a52e-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="9a52e-109">哈希算法的标识符 (类型的`ALG_ID`，如 WinCrypt.h 中定义) 的公钥。</span><span class="sxs-lookup"><span data-stu-id="9a52e-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="9a52e-110">以字节为单位的密钥长度。</span><span class="sxs-lookup"><span data-stu-id="9a52e-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="9a52e-111">包含返回的 CryptoAPI 的格式中的密钥值的变量长度的字节数组。</span><span class="sxs-lookup"><span data-stu-id="9a52e-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a52e-112">备注</span><span class="sxs-lookup"><span data-stu-id="9a52e-112">Remarks</span></span>  
 <span data-ttu-id="9a52e-113">`PublicKeyBlob`结构由[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)， [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)，和其他强名称的函数以表示公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="9a52e-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a52e-114">惠?</span><span class="sxs-lookup"><span data-stu-id="9a52e-114">Requirements</span></span>  
 <span data-ttu-id="9a52e-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a52e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a52e-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9a52e-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9a52e-117">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9a52e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a52e-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a52e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a52e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a52e-119">See Also</span></span>  
 [<span data-ttu-id="9a52e-120">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="9a52e-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="9a52e-121">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="9a52e-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="9a52e-122">强命名结构</span><span class="sxs-lookup"><span data-stu-id="9a52e-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
