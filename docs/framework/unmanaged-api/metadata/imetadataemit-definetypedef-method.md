---
title: "IMetaDataEmit::DefineTypeDef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeDef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a344f592b47d452b4d016f08cefddda650128188
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef 方法
创建一个类型定义的公共语言运行时类型，并获取该类型定义元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szTypeDef`  
 [in]以 Unicode 类型的名称。  
  
 `dwTypeDefFlags`  
 [in]`TypeDef`属性。 这是一个位掩码的`CoreTypeAttr`值。  
  
 `tkExtends`  
 [in]基本类的标记。 它必须是`mdTypeDef`或`mdTypeRef`令牌。  
  
 `rtkImplements`  
 [in]指定此类或接口实现的接口的令牌的数组。  
  
 `ptd`  
 [out]`mdTypeDef`分配的令牌。  
  
## <a name="remarks"></a>备注  
 一个标志`dwTypeDefFlags`指定正在创建的类型是通用类型系统引用类型 （类或接口） 还是通用类型系统值类型。  
  
 根据提供的参数，此方法的副作用，还可以创建`mdInterfaceImpl`记录为每个接口继承或实现是用这种类型。 但是，，此方法不返回任何这些`mdInterfaceImpl`令牌。 如果客户端想要以后添加或修改`mdInterfaceImpl`令牌，它必须使用`IMetaDataImport`接口来枚举它们。 如果你想要使用的 COM 语义`[default]`接口，还应为中的第一个元素提供的默认接口`rtkImplements`; 在类上设置的自定义特性将指示此类具有的默认接口 (其始终被假定为第一次`mdInterfaceImpl`类声明的令牌)。  
  
 每个元素`rtkImplements`数组`mdTypeDef`或`mdTypeRef`令牌。 数组中的最后一个元素必须是`mdTokenNil`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
