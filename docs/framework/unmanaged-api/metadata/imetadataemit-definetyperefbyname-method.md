---
title: IMetaDataEmit::DefineTypeRefByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4dd08afba664a491b3ba398f3da4c6a73cda5378
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517131"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName 方法
获取在指定范围内，这是当前作用域之外定义的类型的元数据令牌。  
  
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
 [in]指定解析范围标记。 以下令牌类型是有效的：  
  
-   `mdModuleRef`如果类型在其中定义调用方在同一程序集中定义的。  
  
-   `mdAssemblyRef`如果不是在其中定义调用方的程序集中定义的类型。  
  
-   `mdTypeRef`如果该类型是嵌套的类型。  
  
-   `mdModule`如果在其中定义调用方位于同一模块中定义该类型。  
  
-   如果全局定义的类型，则为 null。  
  
 `szName`  
 [in]以 unicode 格式的目标类型的名称。  
  
 `ptr`  
 [out]一个指向`mdTypeRef`分配给类型的令牌。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
