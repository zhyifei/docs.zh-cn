---
title: "ICLRStrongName::StrongNameKeyGen 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13eef3e4c0cf4aa8de55aa96335e570ef1985e9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a>ICLRStrongName::StrongNameKeyGen 方法
创建强名称使用新的公钥/私钥密钥对。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszKeyContainer`  
 [in]请求的密钥容器名称中。 `wszKeyContainer`必须非空字符串或 null，以生成一个临时名称。  
  
 `dwFlags`  
 [in]一个值，指定是否保留注册密钥。 支持以下值：  
  
-   0x00000000-时使用`wszKeyContainer`为 null 来生成临时密钥容器名称。  
  
-   0x00000001 (`SN_LEAVE_KEY`)-指定应保持注册密钥。  
  
 `ppbKeyBlob`  
 [out]返回的公钥/私钥对。  
  
 `pcbKeyBlob`  
 [out]大小，以字节为单位的`ppbKeyBlob`。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。  
  
## <a name="remarks"></a>备注  
 [Iclrstrongname:: Strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)方法创建一个 1024年位密钥。 检索到密钥后，应调用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法来释放分配的内存。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [StrongNameKeyGenEx 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
