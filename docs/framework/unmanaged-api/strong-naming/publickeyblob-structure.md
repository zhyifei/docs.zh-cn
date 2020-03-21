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
# <a name="publickeyblob-structure"></a>PublicKeyBlob 结构
以二进制格式表示公钥/私钥对的公钥。  
  
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
  
|成员|说明|  
|------------|-----------------|  
|`SigAlgId`|公钥的签名算法（类型`ALG_ID`，如 WinCrypt.h 中定义的）的标识符。|  
|`HashAlgId`|公钥的哈希算法（类型`ALG_ID`，在 WinCrypt.h 中定义）的标识符。|  
|`cbPublicKey`|键的长度（以字节为单位）。|  
|`PublicKey`|一个可变长度字节数组，包含 CryptoAPI 返回的格式中的键值。|  
  
## <a name="remarks"></a>备注  
 该`PublicKeyBlob`结构由[StrongNameGetPublicKey、](strongnamegetpublickey-function.md)[强名称签名生成](strongnamesignaturegeneration-function.md)和其他强名称函数使用，以表示公钥/私钥对的公钥。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** 强名称.h  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameGetPublicKey 函数](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration 函数](strongnamesignaturegeneration-function.md)
