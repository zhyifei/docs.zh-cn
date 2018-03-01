---
title: "StrongNameKeyDelete 函数"
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
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d3acd8ae5f330e23642a679962a04ccb4f7e8ec6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeydelete-function"></a>StrongNameKeyDelete 函数
删除指定的密钥容器。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamekeydelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszKeyContainer`  
 [in]要删除的密钥容器的名称。  
  
## <a name="return-value"></a>返回值  
 `true`在成功完成;否则为`false`。  
  
## <a name="remarks"></a>备注  
 使用[StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)函数来 importa 公钥/私钥对到容器。  
  
 如果`StrongNameKeyDelete`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameKeyDelete 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [StrongNameKeyInstall 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
