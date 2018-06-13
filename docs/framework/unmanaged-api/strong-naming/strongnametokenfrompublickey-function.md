---
title: StrongNameTokenFromPublicKey 函数
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb8ff76da288975ef291d226bb1f205e73a64252
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460283"
---
# <a name="strongnametokenfrompublickey-function"></a>StrongNameTokenFromPublicKey 函数
获取表示公钥的标记。 强名称标记是公钥的缩写形式。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbPublicKeyBlob`  
 [in]类型的结构[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)包含用于生成强名称签名的密钥对的公共部分。  
  
 `cbPublicKeyBlob`  
 [in]大小，以字节为单位的`pbPublicKeyBlob`。  
  
 `ppbStrongNameToken`  
 [out]强名称标记的键对应传递中`pbPublicKeyBlob`。 公共语言运行时分配的内存中要返回的标记。 调用方必须释放此内存通过使用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数。  
  
 `pcbStrongNameToken`  
 [out]以字节为单位，返回的强名称标记的大小。  
  
## <a name="return-value"></a>返回值  
 `true` 在成功完成;否则为`false`。  
  
## <a name="remarks"></a>备注  
 强名称标记是公钥的用于存储在元数据中的密钥信息时节省空间的缩写形式。 具体而言，强名称令牌将用于程序集引用来引用依赖程序集。  
  
 如果`StrongNameTokenFromPublicKey`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：** 作为 mscoree.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameTokenFromPublicKey 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [StrongNameGetPublicKey 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [PublicKeyBlob Strong Naming](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
