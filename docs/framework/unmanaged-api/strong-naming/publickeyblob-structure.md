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
ms.openlocfilehash: fd7a4b19613ea771a055af7dd91ec368859ee191
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43475967"
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob 结构
以二进制格式表示的公钥/私钥对的公钥。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`SigAlgId`|签名算法的标识符 (类型的`ALG_ID`WinCrypt.h 中定义) 的公钥。|  
|`HashAlgId`|哈希算法的标识符 (类型的`ALG_ID`WinCrypt.h 中定义) 的公钥。|  
|`cbPublicKey`|以字节为单位的密钥的长度。|  
|`PublicKey`|包含返回 CryptoAPI 的格式中的密钥值的长度可变的字节数组。|  
  
## <a name="remarks"></a>备注  
 `PublicKeyBlob`结构可供[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)， [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)，和其他强名称的函数来表示公钥/私钥对的公钥。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameGetPublicKey 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [StrongNameSignatureGeneration 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [强命名结构](https://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
