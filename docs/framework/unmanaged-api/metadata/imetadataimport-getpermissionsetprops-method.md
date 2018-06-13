---
title: IMetaDataImport::GetPermissionSetProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be9b2fa3037dc00bce52d9ff89291d1c02cffc38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449294"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a>IMetaDataImport::GetPermissionSetProps 方法
获取与关联的元数据<xref:System.Security.PermissionSet?displayProperty=nameWithType>由指定的 Permission 标记表示。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pm`  
 [in]表示要获取的元数据属性的权限集权限元数据标记。  
  
 `pdwAction`  
 [out]指向的权限集的指针。  
  
 `ppvPermission`  
 [out]指向的权限集的二进制元数据签名的指针。  
  
 `pcbPermission`  
 [out]以字节为单位的大小`ppvPermission`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Security.PermissionSet>  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
