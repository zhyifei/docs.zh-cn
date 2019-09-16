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
# <a name="publickeyblob-structure"></a>PublicKeyBlob 结构
表示公钥/私钥对的公钥，采用二进制格式。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
|`SigAlgId`|公钥的签名算法的标识符（类型`ALG_ID`为，如 wincrypt.h 中所定义）。|  
|`HashAlgId`|公钥的哈希算法的标识符（类型`ALG_ID`为，在 wincrypt.h 中定义）。|  
|`cbPublicKey`|密钥的长度（以字节为单位）。|  
|`PublicKey`|可变长度的字节数组，其中包含由 CryptoAPI 返回的格式的键值。|  
  
## <a name="remarks"></a>备注  
 `PublicKeyBlob`结构由 [StrongNameGetPublicKey](strongnamegetpublickey-function.md)、 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)和其他强名称函数用来表示公钥/私钥对的公钥。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameGetPublicKey 函数](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration 函数](strongnamesignaturegeneration-function.md)
