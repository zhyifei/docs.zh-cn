---
title: ICLRStrongName::StrongNameKeyGenEx 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
ms.openlocfilehash: b09677a45c5d515aacb2cac709599140039a9dd8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899558"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a>ICLRStrongName::StrongNameKeyGenEx 方法
使用指定的密钥大小生成新的公钥/私钥对，以便使用强名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszKeyContainer`  
 中请求的密钥容器名称。 `wszKeyContainer` 必须为非空字符串或 null，才能生成临时名称。  
  
 `dwFlags`  
 中一个值，该值指定是否保留注册的密钥。 支持以下值：  
  
- 0x00000000-在 `wszKeyContainer` 为 null 时使用，以生成临时密钥容器名称。  
  
- 0x00000001 （`SN_LEAVE_KEY`）-指定密钥应为 "已注册"。  
  
 `dwKeySize`  
 中请求的密钥大小，以位为单位。  
  
 `ppbKeyBlob`  
 弄返回的公钥/私钥对。  
  
 `pcbKeyBlob`  
 弄`ppbKeyBlob`的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。  
  
## <a name="remarks"></a>备注  
 .NET Framework 版本1.0 和1.1 需要 `dwKeySize` 1024 位才能使用强名称为程序集签名;版本2.0 添加了对2048位密钥的支持。  
  
 检索到密钥后，应调用[ICLRStrongName：： StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法来释放已分配的内存。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameKeyGen 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
