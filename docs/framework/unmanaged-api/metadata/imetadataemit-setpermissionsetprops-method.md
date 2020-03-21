---
title: IMetaDataEmit::SetPermissionSetProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: de4cfdf2a9353eebdebaf4df9e481d06d776ff04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177492"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>IMetaDataEmit::SetPermissionSetProps 方法
设置或更新由之前调用[IMetaDataEmit：:Define许可集](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)定义的权限集的元数据签名的功能。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a>parameters  
 `tk`  
 [在]表示要修饰的对象的元数据令牌。  
  
 `dwAction`  
 [在]指定要使用的声明性安全性类型的[CorDecl 安全](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)值。  
  
 `pvPermission`  
 [在]权限 BLOB。  
  
 `cbPermission`  
 [在]的大小（以字节为单位）的大小`pvPermission`。  
  
 `ppm`  
 [出]表示`mdPermission`更新权限的元数据令牌。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
