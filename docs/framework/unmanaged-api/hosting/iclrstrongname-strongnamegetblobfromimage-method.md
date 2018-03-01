---
title: "ICLRStrongName::StrongNameGetBlobFromImage 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff2ec30068903397d9f8d736f4f270c8d3c1669f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a>ICLRStrongName::StrongNameGetBlobFromImage 方法
获取位于指定的内存地址处的二进制表示形式的程序集映像。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbBase`  
 [in]映射程序集清单内存地址。  
  
 `dwLength`  
 [in]大小，以字节为单位，在图像的`pbBase`。  
  
 `pbBlob`  
 [in]用于包含图像的二进制表示的缓冲区。  
  
 `pcbBlob`  
 [在中，out]请求的最大大小，以字节为单位， `pbBlob`。 返回时，实际大小，以字节为单位的`pbBlob`。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameGetBlob 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
