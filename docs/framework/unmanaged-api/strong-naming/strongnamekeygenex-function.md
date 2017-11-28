---
title: "StrongNameKeyGenEx 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyGenEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyGenEx
helpviewer_keywords: StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 87841c230c71650f822a6cb2f6cc3f3c17c2ef35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeygenex-function"></a>StrongNameKeyGenEx 函数
生成与指定的密钥大小，供强名称使用新的公钥/私钥密钥对。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamekeygenex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszKeyContainer`  
 [in]请求的密钥容器名称中。 `wszKeyContainer`必须为非空字符串，或为 null，表示生成一个临时名称。  
  
 `dwFlags`  
 [in]指定是否保留注册密钥。 支持以下值：  
  
-   0x00000000-时使用`wszKeyContainer`为 null 来生成临时密钥容器名称。  
  
-   0x00000001 (`SN_LEAVE_KEY`)-指定应保持注册密钥。  
  
 `dwKeySize`  
 [in]请求的密钥，以位为单位的密钥的大小。  
  
 `ppbKeyBlob`  
 [out]返回的公钥/私钥对。  
  
 `pcbKeyBlob`  
 [out]大小，以字节为单位的`ppbKeyBlob`。  
  
## <a name="return-value"></a>返回值  
 `true`在成功完成;否则为`false`。  
  
## <a name="remarks"></a>备注  
 .NET framework 1.0 和 1.1 版需要`dwKeySize`1024 位，强名称; 程序集进行签名的版本 2.0 添加为 2048年位密钥的支持。  
  
 检索到密钥后，应调用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数释放分配的内存。  
  
 如果`StrongNameKeyGenEx`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [StrongNameKeyGenEx 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [StrongNameKeyGen 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
