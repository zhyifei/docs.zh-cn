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
ms.openlocfilehash: 8943df861b1bff2b28c68d0233fc336d1b5d4579
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798944"
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
  
- `SN_INFLAG_FORCE_VER`（0x00000001）-即使需要重写注册表设置，也强制进行验证。  
  
- `SN_INFLAG_INSTALL`（0x00000002）-指定这是第一次验证清单。  
  
- `SN_INFLAG_ADMIN_ACCESS`（0x00000004）-指定缓存只允许具有管理权限的用户访问。  
  
- `SN_INFLAG_USER_ACCESS`（0x00000008）-指定只有当前用户才能访问程序集。  
  
- `SN_INFLAG_ALL_ACCESS`（0x00000010）-指定缓存将不提供访问限制。  
  
- `SN_INFLAG_RUNTIME`（0x80000000）-保留用于内部调试。  
  
 `pdwOutFlags`  
 弄指示强名称签名是否已验证的标志。 支持以下值：  
  
- `SN_OUTFLAG_WAS_VERIFIED`（0x00000001）-将此值设置为`false` ，以指定验证由于注册表设置而成功。  
  
## <a name="return-value"></a>返回值  
 `true`如果验证成功，则为;否则为`false`。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameSignatureVerification 方法](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [StrongNameSignatureVerificationEx 方法](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
