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
ms.openlocfilehash: e66196e2bd2cb326ca3f5badc67bcf8d81e5fc3c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799172"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="d803f-102">PublicKeyBlob 结构</span><span class="sxs-lookup"><span data-stu-id="d803f-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="d803f-103">表示公钥/私钥对的公钥，采用二进制格式。</span><span class="sxs-lookup"><span data-stu-id="d803f-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d803f-104">语法</span><span class="sxs-lookup"><span data-stu-id="d803f-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="d803f-105">成员</span><span class="sxs-lookup"><span data-stu-id="d803f-105">Members</span></span>  
  
|<span data-ttu-id="d803f-106">成员</span><span class="sxs-lookup"><span data-stu-id="d803f-106">Member</span></span>|<span data-ttu-id="d803f-107">描述</span><span class="sxs-lookup"><span data-stu-id="d803f-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="d803f-108">公钥的签名算法的标识符（类型`ALG_ID`为，如 wincrypt.h 中所定义）。</span><span class="sxs-lookup"><span data-stu-id="d803f-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="d803f-109">公钥的哈希算法的标识符（类型`ALG_ID`为，在 wincrypt.h 中定义）。</span><span class="sxs-lookup"><span data-stu-id="d803f-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="d803f-110">密钥的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d803f-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="d803f-111">可变长度的字节数组，其中包含由 CryptoAPI 返回的格式的键值。</span><span class="sxs-lookup"><span data-stu-id="d803f-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d803f-112">备注</span><span class="sxs-lookup"><span data-stu-id="d803f-112">Remarks</span></span>  
 <span data-ttu-id="d803f-113">`PublicKeyBlob`结构由 [StrongNameGetPublicKey](strongnamegetpublickey-function.md)、 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)和其他强名称函数用来表示公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="d803f-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d803f-114">要求</span><span class="sxs-lookup"><span data-stu-id="d803f-114">Requirements</span></span>  
 <span data-ttu-id="d803f-115">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d803f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d803f-116">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="d803f-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d803f-117">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d803f-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d803f-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d803f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d803f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d803f-119">See also</span></span>

- [<span data-ttu-id="d803f-120">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="d803f-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="d803f-121">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="d803f-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
