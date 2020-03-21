---
title: IMetaDataAssemblyEmit::DefineManifestResource 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 5aa5d78faa8ca9261594e2a649b11088e1d78ee7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177859"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>IMetaDataAssemblyEmit::DefineManifestResource 方法
创建包含指定清单资源的元数据的 `ManifestResource` 结构，并返回关联的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a>parameters  
 `szName`  
 [在]资源的名称。  
  
 `tkImplementation`  
 [在]类型的`mdtFile`元数据令牌或`mdtAssemblyRef`映射到资源提供程序的元数据令牌。 NULL 值表示嵌入元数据的文件是资源提供程序。  
  
 `dwOffset`  
 [在]文件中资源开头的偏移量。 对于独立文件中的资源，这始终为零。 如果资源嵌入到 PE（可移植可执行文件）文件中，这是资源 BLOB 的偏移量，它从 cor.h 标头文件中指定的位置开始。  
  
 `dwResourceFlags`  
 [在]指定资源定义的属性设置的标志值的位组合。  
  
 `pmdmr`  
 [出]指向返回的元数据令牌的指针。  
  
## <a name="remarks"></a>备注  
 必须`ManifestResource`为每个程序集文件中实现的每个资源定义一个元数据结构。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
