---
title: IMetaDataAssemblyImport::GetManifestResourceProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177660"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps 方法
使用指定的元数据签名获取清单资源的属性集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a>parameters  
 `mdmr`  
 [在]表示`mdManifestResource`要为其获取属性的资源的令牌。  
  
 `szName`  
 [出]资源的名称。  
  
 `cchName`  
 [在]大字符的大小`szName`。  
  
 `pchName`  
 [出]指向 中实际返回的宽字符数的指针`szName`。  
  
 `ptkImplementation`  
 [出]指向分别表示包含`mdFile`资源的文件或`mdAssemblyRef`程序集的令牌或令牌的指针。  
  
 `pdwOffset`  
 [出]指向指定偏移到文件中资源开头的值的指针。  
  
 `pdwResourceFlags`  
 [出]指向用于描述应用于资源的元数据的标志的指针。 标志值是一个或多个[CorManifest 资源标志](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md)值的组合。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
