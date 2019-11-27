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
ms.openlocfilehash: 83170815f4aa65988bb6a6394bd466a0ba376ebf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432051"
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
  
## <a name="parameters"></a>参数  
 `szName`  
 中资源的名称。  
  
 `tkImplementation`  
 中映射到资源提供程序 `mdtFile` 或 `mdtAssemblyRef` 类型的元数据标记。 NULL 值指示嵌入元数据的文件是资源提供程序。  
  
 `dwOffset`  
 中文件中资源的起始位置的偏移量。 对于独立文件中的资源，此值将始终为零。 如果资源嵌入在 PE （可移植可执行文件）文件中，则这是资源 BLOB 的偏移量，它从 cor 头文件中指定的位置开始。  
  
 `dwResourceFlags`  
 中指定资源定义的属性设置的标志值的按位组合。  
  
 `pmdmr`  
 弄指向返回的元数据标记的指针。  
  
## <a name="remarks"></a>备注  
 必须为每个在程序集的文件中实现的每个资源定义一个 `ManifestResource` 的元数据结构。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
