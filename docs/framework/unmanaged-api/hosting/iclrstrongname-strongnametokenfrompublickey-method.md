---
title: "ICLRStrongName::StrongNameTokenFromPublicKey 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameTokenFromPublicKey
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84f47fcef7c896b197de410234694c211d07c30b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>ICLRStrongName::StrongNameTokenFromPublicKey 方法
获取令牌表示的公共密钥。 强名称标记是公钥的缩写形式。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StrongNameTokenFromPublicKey (   
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
 [out]强名称标记的键对应传递中`pbPublicKeyBlob`。 公共语言运行时分配的内存中要返回的标记。 调用方必须释放此内存通过使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。  
  
 `pcbStrongNameToken`  
 [out]以字节为单位，返回的强名称标记的大小。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。  
  
## <a name="remarks"></a>备注  
 强名称标记是公钥的用于存储在元数据中的密钥信息时节省空间的缩写形式。 具体而言，强名称令牌将用于程序集引用来引用依赖程序集。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 mscoree.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [StrongNameGetPublicKey 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [PublicKeyBlob 结构](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
