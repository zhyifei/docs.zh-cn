---
title: ICLRStrongName::StrongNameTokenFromPublicKey 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: e61a652072b424d1245518c832f9b0856e0f2021
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762599"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>ICLRStrongName::StrongNameTokenFromPublicKey 方法
获取表示公钥的标记。 强名称标记是公钥的缩写形式。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>参数  
 `pbPublicKeyBlob`  
 中[PublicKeyBlob](../strong-naming/publickeyblob-structure.md)类型的结构，它包含用于生成强名称签名的密钥对的公共部分。  
  
 `cbPublicKeyBlob`  
 中的大小（以字节为单位） `pbPublicKeyBlob` 。  
  
 `ppbStrongNameToken`  
 弄与传入的密钥对应的强名称标记 `pbPublicKeyBlob` 。 公共语言运行时分配要在其中返回标记的内存。 调用方必须通过使用[ICLRStrongName：： StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md)方法释放此内存。  
  
 `pcbStrongNameToken`  
 弄返回的强名称标记的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。  
  
## <a name="remarks"></a>注解  
 强名称标记是用于在元数据中存储密钥信息时节省空间的公钥的缩写形式。 具体而言，强名称令牌在程序集引用中用于引用依赖程序集。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameGetPublicKey 方法](iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob 结构](../strong-naming/publickeyblob-structure.md)
- [ICLRStrongName 接口](iclrstrongname-interface.md)
