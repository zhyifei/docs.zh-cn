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
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140616"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="290e0-102">PublicKeyBlob 结构</span><span class="sxs-lookup"><span data-stu-id="290e0-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="290e0-103">表示公钥/私钥对的公钥，采用二进制格式。</span><span class="sxs-lookup"><span data-stu-id="290e0-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="290e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="290e0-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="290e0-105">Members</span><span class="sxs-lookup"><span data-stu-id="290e0-105">Members</span></span>  
  
|<span data-ttu-id="290e0-106">成员</span><span class="sxs-lookup"><span data-stu-id="290e0-106">Member</span></span>|<span data-ttu-id="290e0-107">描述</span><span class="sxs-lookup"><span data-stu-id="290e0-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="290e0-108">公钥的签名算法的标识符（类型 `ALG_ID`，如 Wincrypt.h 中所定义）。</span><span class="sxs-lookup"><span data-stu-id="290e0-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="290e0-109">公钥的哈希算法的标识符（类型 `ALG_ID`，如 Wincrypt.h 中所定义）。</span><span class="sxs-lookup"><span data-stu-id="290e0-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="290e0-110">密钥的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="290e0-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="290e0-111">可变长度的字节数组，其中包含由 CryptoAPI 返回的格式的键值。</span><span class="sxs-lookup"><span data-stu-id="290e0-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="290e0-112">备注</span><span class="sxs-lookup"><span data-stu-id="290e0-112">Remarks</span></span>  
 <span data-ttu-id="290e0-113">[StrongNameGetPublicKey](strongnamegetpublickey-function.md)、 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)和其他强名称函数使用 `PublicKeyBlob` 结构来表示公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="290e0-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="290e0-114">要求</span><span class="sxs-lookup"><span data-stu-id="290e0-114">Requirements</span></span>  
 <span data-ttu-id="290e0-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="290e0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="290e0-116">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="290e0-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="290e0-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="290e0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="290e0-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="290e0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290e0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="290e0-119">See also</span></span>

- [<span data-ttu-id="290e0-120">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="290e0-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="290e0-121">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="290e0-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
