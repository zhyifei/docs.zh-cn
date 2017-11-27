---
title: "IMetaDataEmit::DefineTypeRefByName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ce04733fa9f149f155d850c53b65b263943cf8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName 方法
获取定义在指定范围内，这是当前作用域之外的类型元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a>参数  
 `tkResolutionScope`  
 [in]指定解析范围令牌。 以下令牌类型为有效值：  
  
-   `mdModuleRef`如果在其中定义调用方位于同一程序集中定义的类型。  
  
-   `mdAssemblyRef`如果在不是在其中定义调用方的程序集中定义的类型。  
  
-   `mdTypeRef`如果该类型是嵌套的类型。  
  
-   `mdModule`如果在其中定义调用方的相同模块中定义的类型。  
  
-   如果全局定义的类型，则为 null。  
  
 `szName`  
 [in]Unicode 中的目标类型的名称。  
  
 `ptr`  
 [out]指向的指针`mdTypeRef`分配给类型的令牌。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
