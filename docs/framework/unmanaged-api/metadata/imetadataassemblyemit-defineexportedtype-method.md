---
title: IMetaDataAssemblyEmit::DefineExportedType 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2eb894a8bac702c30826d1e965c91cae9b259ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType 方法
创建包含指定导出类型的元数据的 `ExportedType` 结构，并返回关联的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szName`  
 [in]要导出的类型的名称。 版本 1.1 的公共语言运行时，导出类型的名称必须完全匹配中给定的名称`TypeDef`类型。  
  
 `tkImplementation`  
 [in]指定导出的类型实现了一个令牌。 有效的值和其关联的含义是：  
  
-   `mdFile` 类型是此程序集内的不同文件中实现的。  
  
-   `mdAssemblyRef` 类型是在不同的程序集中实现的。  
  
-   `mdExportedTYpe` 类型嵌套在其他类型。  
  
-   `mdFileNil` 类型在与清单相同的文件，并不是嵌套的类型。  
  
 `tkTypeDef`  
 [in]指定要导出的类型的元数据标记。 在输入此值`TypeDef`中的文件，可实现类型并仅当该文件处于此程序集相关的表。  
  
 `dwExportedTypeFlags`  
 [in]按位组合[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)定义导出的类型的属性设置的枚举值。  
  
 `pmdct`  
 [out]指向返回的元数据令牌，该值指示导出的类型的指针。  
  
## <a name="remarks"></a>备注  
 `ExportedType`必须为每个，则公开此程序集和实现中不包含清单的模块类型定义元数据结构。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
