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
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176950"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="088e1-102">PublicKeyBlob 结构</span><span class="sxs-lookup"><span data-stu-id="088e1-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="088e1-103">以二进制格式表示公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="088e1-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="088e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="088e1-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="088e1-105">成员</span><span class="sxs-lookup"><span data-stu-id="088e1-105">Members</span></span>  
  
|<span data-ttu-id="088e1-106">成员</span><span class="sxs-lookup"><span data-stu-id="088e1-106">Member</span></span>|<span data-ttu-id="088e1-107">说明</span><span class="sxs-lookup"><span data-stu-id="088e1-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="088e1-108">公钥的签名算法（类型`ALG_ID`，如 WinCrypt.h 中定义的）的标识符。</span><span class="sxs-lookup"><span data-stu-id="088e1-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="088e1-109">公钥的哈希算法（类型`ALG_ID`，在 WinCrypt.h 中定义）的标识符。</span><span class="sxs-lookup"><span data-stu-id="088e1-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="088e1-110">键的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="088e1-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="088e1-111">一个可变长度字节数组，包含 CryptoAPI 返回的格式中的键值。</span><span class="sxs-lookup"><span data-stu-id="088e1-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="088e1-112">备注</span><span class="sxs-lookup"><span data-stu-id="088e1-112">Remarks</span></span>  
 <span data-ttu-id="088e1-113">该`PublicKeyBlob`结构由[StrongNameGetPublicKey、](strongnamegetpublickey-function.md)[强名称签名生成](strongnamesignaturegeneration-function.md)和其他强名称函数使用，以表示公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="088e1-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="088e1-114">要求</span><span class="sxs-lookup"><span data-stu-id="088e1-114">Requirements</span></span>  
 <span data-ttu-id="088e1-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="088e1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="088e1-116">**标题：** 强名称.h</span><span class="sxs-lookup"><span data-stu-id="088e1-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="088e1-117">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="088e1-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="088e1-118">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="088e1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088e1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="088e1-119">See also</span></span>

- [<span data-ttu-id="088e1-120">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="088e1-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="088e1-121">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="088e1-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
