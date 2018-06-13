---
title: PublicKeyBlob 结构
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7577a24a023c38370f5ac1f8c471ce31409e75d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459334"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="afad4-102">PublicKeyBlob 结构</span><span class="sxs-lookup"><span data-stu-id="afad4-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="afad4-103">以二进制格式表示公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="afad4-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afad4-104">语法</span><span class="sxs-lookup"><span data-stu-id="afad4-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="afad4-105">成员</span><span class="sxs-lookup"><span data-stu-id="afad4-105">Members</span></span>  
  
|<span data-ttu-id="afad4-106">成员</span><span class="sxs-lookup"><span data-stu-id="afad4-106">Member</span></span>|<span data-ttu-id="afad4-107">描述</span><span class="sxs-lookup"><span data-stu-id="afad4-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="afad4-108">签名算法的标识符 (类型的`ALG_ID`，如 WinCrypt.h 中定义) 的公钥。</span><span class="sxs-lookup"><span data-stu-id="afad4-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="afad4-109">哈希算法的标识符 (类型的`ALG_ID`，如 WinCrypt.h 中定义) 的公钥。</span><span class="sxs-lookup"><span data-stu-id="afad4-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="afad4-110">以字节为单位的密钥长度。</span><span class="sxs-lookup"><span data-stu-id="afad4-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="afad4-111">包含返回的 CryptoAPI 的格式中的密钥值的变量长度的字节数组。</span><span class="sxs-lookup"><span data-stu-id="afad4-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afad4-112">备注</span><span class="sxs-lookup"><span data-stu-id="afad4-112">Remarks</span></span>  
 <span data-ttu-id="afad4-113">`PublicKeyBlob`结构由[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)， [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)，和其他强名称的函数以表示公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="afad4-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afad4-114">要求</span><span class="sxs-lookup"><span data-stu-id="afad4-114">Requirements</span></span>  
 <span data-ttu-id="afad4-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="afad4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afad4-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="afad4-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="afad4-117">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="afad4-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="afad4-118">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afad4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afad4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="afad4-119">See Also</span></span>  
 [<span data-ttu-id="afad4-120">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="afad4-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="afad4-121">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="afad4-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="afad4-122">强命名结构</span><span class="sxs-lookup"><span data-stu-id="afad4-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
