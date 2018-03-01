---
title: "StrongNameKeyInstall 函数"
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
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9a8dbc84f375b7bbbad47971936650d81c5c63df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall 函数
将公钥/私钥对导入容器。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszKeyContainer`  
 [in]密钥容器的名称。 `wszKeyContainer`必须非空字符串。  
  
 `pbKeyBlob`  
 [in]二进制的密钥对。  
  
 `cbKeyBlob`  
 [in]大小，以字节为单位的`pbKeyBlob`。  
  
## <a name="return-value"></a>返回值  
 `true`在成功完成;否则为`false`。  
  
## <a name="remarks"></a>备注  
 使用[StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)函数来删除密钥容器。  
  
 如果`StrongNameKeyInstall`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。  
  
## <a name="requirements"></a>惠?  
 **平台：** WindSee[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameKeyInstall 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [StrongNameKeyDelete 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
