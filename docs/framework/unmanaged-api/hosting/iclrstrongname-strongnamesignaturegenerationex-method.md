---
title: ICLRStrongName::StrongNameSignatureGenerationEx 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bf9a94c55258193e3172459da129ba16f9c3265
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435432"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a>ICLRStrongName::StrongNameSignatureGenerationEx 方法
为指定的程序集中，根据指定的标志生成的强名称签名。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszFilePath`  
 [in]包含将为其生成强名称签名的程序集清单文件的路径。  
  
 `wszKeyContainer`  
 [in]包含公钥/私钥对的密钥容器的名称。  
  
 如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 中有效的容器。 在这种情况下，存储在容器的密钥对用于对文件进行签名。  
  
 如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。  
  
 `pbKeyBlob`  
 [in]指向公钥/私钥对的指针。 此对采用以下格式创建由 Win32`CryptExportKey`函数。 如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。  
  
 `cbKeyBlob`  
 [in]大小，以字节为单位的`pbKeyBlob`。  
  
 `ppbSignatureBlob`  
 [out]指向公共语言运行时向其返回签名的位置的指针。 如果`ppbSignatureBlob`是 null，运行时将签名存储在指定的文件中`wszFilePath`。  
  
 如果`ppbSignatureBlob`是不为 null，公共语言运行时分配的空间内进行返回签名。 调用方必须释放此空间使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。  
  
 `pcbSignatureBlob`  
 [out]以字节为单位，返回签名的大小。  
  
 `dwFlags`  
 [in]一个或多个以下值：  
  
-   `SN_SIGN_ALL_FILES` (0x00000001)-重新计算所有链接的模块的哈希值。  
  
-   `SN_TEST_SIGN` (0x00000002) — 程序集进行测试签名。  
  
## <a name="return-value"></a>返回值  
 `S_OK` 如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。  
  
## <a name="remarks"></a>备注  
 指定为空`wszFilePath`来计算而无需创建签名的签名的大小。  
  
 可以直接在文件中，存储或返回到调用方的签名。  
  
 如果`SN_SIGN_ALL_FILES`指定但不包含的公共密钥 (同时`pbKeyBlob`和`wszFilePath`都为 null 时)，重新计算链接的模块的哈希值，但该程序集未重新签名。  
  
 如果`SN_TEST_SIGN`指定，则不会修改公共语言运行时标头以指示程序集使用强名称签名。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameSignatureGeneration 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
