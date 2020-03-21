---
title: ICLRStrongName::StrongNameSignatureGeneration 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178041"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>ICLRStrongName::StrongNameSignatureGeneration 方法
为指定的程序集生成强名称签名。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>parameters  
 `wszFilePath`  
 [在]包含将为其生成强名称签名的程序集清单的文件的路径。  
  
 `wszKeyContainer`  
 [在]包含公钥/私钥对的密钥容器的名称。  
  
 如果`pbKeyBlob`为 null，`wszKeyContainer`则必须在加密服务提供商 （CSP） 中指定有效的容器。 在这种情况下，存储在容器中的密钥对用于对文件进行签名。  
  
 如果`pbKeyBlob`不是空，则假定密钥对包含在密钥二进制大型对象 （BLOB） 中。  
  
 密钥必须是 1024 位里维斯-沙米尔-阿德尔曼 （RSA） 签名密钥。 目前不支持其他类型的密钥。  
  
 `pbKeyBlob`  
 [在]指向公钥/私钥对的指针。 此对采用 Win32`CryptExportKey`函数创建的格式。 如果`pbKeyBlob`为 null，则假定 指定的`wszKeyContainer`键容器包含密钥对。  
  
 `cbKeyBlob`  
 [在]的大小（以字节为单位）的大小`pbKeyBlob`。  
  
 `ppbSignatureBlob`  
 [出]指向公共语言运行时返回签名的位置的指针。 如果`ppbSignatureBlob`为 null，运行时将签名存储在 指定的`wszFilePath`文件中。  
  
 如果`ppbSignatureBlob`为 null，则通用语言运行时会分配用于返回签名的空间。 调用方必须使用[ICLRStrongNameName：：StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法释放此空间。  
  
 `pcbSignatureBlob`  
 [出]返回的签名的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果方法成功完成;如果方法成功完成;否则，指示失败的 HRESULT 值（请参阅列表[的常用 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。  
  
## <a name="remarks"></a>备注  
 指定 null`wszFilePath`以计算签名的大小而不创建签名。  
  
 签名可以直接存储在文件中，也可以返回到调用方。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MetaHost.h  
  
 **库：** 作为资源包含在 MSCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameSignatureGenerationEx 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
