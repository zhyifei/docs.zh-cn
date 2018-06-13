---
title: StrongNameSignatureVerificationEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ce139669c0a31301f3eecdef4b4d61f83d5e4e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458934"
---
# <a name="strongnamesignatureverificationex-function"></a>StrongNameSignatureVerificationEx 函数
获取一个值，该值在提供的路径的程序集清单是否包含强名称签名。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszFilePath`  
 [in]要验证的程序集的可移植可执行 （.exe 或.dll） 文件路径。  
  
 `fForceVerification`  
 [in]`true`执行验证，即使它是需要重写注册表设置; 否则为`false`。  
  
 `pfWasVerified`  
 [out]`true`强名称签名验证; 否则为如果`false`。 `pfWasVerified` 此外将设置为`false`如果验证成功由于注册表设置。  
  
## <a name="return-value"></a>返回值  
 `true` 如果验证成功，则否则为`false`。  
  
## <a name="remarks"></a>备注  
 `StrongNameSignatureVerificationEx` 提供了类似于一功能[StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)函数。 但是，第二个输入参数和输出参数为`StrongNameSignatureVerificationEx`属于类型`BOOLEAN`而不是`DWORD`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：** 作为 mscoree.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameSignatureVerificationEx 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [StrongNameSignatureVerification 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
