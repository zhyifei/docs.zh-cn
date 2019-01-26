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
ms.openlocfilehash: bdee4df6964097f1c333a8fe96756a8898f7c1cc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598888"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a>IMetaDataImport::GetPermissionSetProps 方法
获取与关联的元数据<xref:System.Security.PermissionSet?displayProperty=nameWithType>所表示的指定权限令牌。  
  
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
 [in]表示要获取其元数据属性的权限集的权限的元数据标记。  
  
 `pdwAction`  
 [out]指向在权限集中的指针。  
  
 `ppvPermission`  
 [out]一个指向权限集的二进制元数据签名。  
  
 `pcbPermission`  
 [out]以字节为单位的大小`ppvPermission`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 包含为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Security.PermissionSet>
- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
