---
title: "IMetaDataAssemblyEmit::DefineManifestResource 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a435c946e13950faad7545e3da78ce373ee7fa0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>IMetaDataAssemblyEmit::DefineManifestResource 方法
创建包含指定清单资源的元数据的 `ManifestResource` 结构，并返回关联的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szName`  
 [in]资源的名称。  
  
 `tkImplementation`  
 [in]类型的元数据标记`mdtFile`或`mdtAssemblyRef`映射到资源提供程序。 一个 NULL 值指示在其中嵌入的元数据文件是资源提供程序。  
  
 `dwOffset`  
 [in]到文件中的资源的开头的偏移量。 对于独立文件中的资源，这将始终为零。 如果资源嵌入到 PE （可移植可执行文件） 文件中，这是资源 BLOB，cor.h 标头文件中指定的位置开始的偏移量。  
  
 `dwResourceFlags`  
 [in]指定的资源定义的属性设置的标志值按位组合。  
  
 `pmdmr`  
 [out]指向返回的元数据标记的指针。  
  
## <a name="remarks"></a>备注  
 一个`ManifestResource`必须为每个程序集的文件中实现的每个资源定义元数据结构。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
