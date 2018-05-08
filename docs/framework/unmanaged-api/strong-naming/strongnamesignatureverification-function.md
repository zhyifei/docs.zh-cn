---
title: StrongNameSignatureVerification 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c888c32a0b40d2458a919613e35ca9d1d830c4f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="strongnamesignatureverification-function"></a>StrongNameSignatureVerification 函数
获取一个值，该值在提供的路径的程序集清单是否包含强名称签名，验证根据指定的标志。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszFilePath`  
 [in]要验证的程序集的可移植可执行文件 （.dll 或.exe） 文件路径。  
  
 `dwInFlags`  
 [in]若要修改的验证行为的标志。 支持以下值：  
  
-   `SN_INFLAG_FORCE_VER` (0x00000001) — 即使需要重写注册表设置强制执行验证。  
  
-   `SN_INFLAG_INSTALL` (0x00000002) — 指定这是首次验证清单。  
  
-   `SN_INFLAG_ADMIN_ACCESS` (0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。  
  
-   `SN_INFLAG_USER_ACCESS` (0x00000008)-指定程序集仅对当前用户可以访问。  
  
-   `SN_INFLAG_ALL_ACCESS` (0x00000010)-指定缓存将提供不能保证的访问限制。  
  
-   `SN_INFLAG_RUNTIME` (0x80000000)-保留供内部调试。  
  
 `pdwOutFlags`  
 [out]标志，指示是否已验证强名称签名。 支持以下值：  
  
-   `SN_OUTFLAG_WAS_VERIFIED` 此值设置为 (0x00000001) —`false`指定验证成功由于注册表设置。  
  
## <a name="return-value"></a>返回值  
 `true` 如果验证成功，则否则为`false`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameSignatureVerification 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [StrongNameSignatureVerificationEx 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
