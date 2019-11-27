---
title: IMetaDataImport::GetScopeProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: af1c3d599c5280e584ffb842c96c70a7c3d4ed08
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436874"
---
# <a name="imetadataimportgetscopeprops-method"></a>IMetaDataImport::GetScopeProps 方法
获取当前元数据范围内的程序集或模块的名称和版本标识符（可选）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a>参数  
 `szName`  
 弄程序集或模块名称的缓冲区。  
  
 `cchName`  
 中`szName`的大小（以宽字符为大小）。  
  
 `pchName`  
 弄`szName`中返回的宽字符数。  
  
 `pmvid`  
 [out，optional]一个指向 GUID 的指针，该 GUID 用于唯一标识程序集或模块的版本。  
  
## <a name="remarks"></a>备注  
 使用[IMetaDataEmit：： SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)方法设置这些属性。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
