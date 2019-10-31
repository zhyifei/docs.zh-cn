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
ms.openlocfilehash: 7dd61be008ba08ca2b28ae3e7e8ff6326f8a41d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129235"
---
# <a name="strongnamesignatureverification-function"></a>StrongNameSignatureVerification 函数
获取一个值，该值指示提供的路径中的程序集清单是否包含根据指定标志验证的强名称签名。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszFilePath`  
 中要验证的程序集的可移植可执行文件（.dll 或 .exe）的路径。  
  
 `dwInFlags`  
 中用于修改验证行为的标志。 支持以下值：  
  
- `SN_INFLAG_FORCE_VER` （0x00000001）-即使需要重写注册表设置，也强制进行验证。  
  
- `SN_INFLAG_INSTALL` （0x00000002）-指定这是第一次验证清单。  
  
- `SN_INFLAG_ADMIN_ACCESS` （0x00000004）-指定缓存只允许具有管理权限的用户访问。  
  
- `SN_INFLAG_USER_ACCESS` （0x00000008）-指定只有当前用户才能访问该程序集。  
  
- `SN_INFLAG_ALL_ACCESS` （0x00000010）-指定缓存将不提供访问限制。  
  
- `SN_INFLAG_RUNTIME` （0x80000000）-保留用于内部调试。  
  
 `pdwOutFlags`  
 弄指示强名称签名是否已验证的标志。 支持以下值：  
  
- `SN_OUTFLAG_WAS_VERIFIED` （0x00000001）-此值设置为 `false` 以指定验证是否已成功（因为注册表设置）。  
  
## <a name="return-value"></a>返回值  
 如果验证成功，则 `true`;否则，`false`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameSignatureVerification 方法](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [StrongNameSignatureVerificationEx 方法](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
