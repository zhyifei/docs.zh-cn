---
title: IMetaDataEmit::SetTypeDefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177464"
---
# <a name="imetadataemitsettypedefprops-method"></a>IMetaDataEmit::SetTypeDefProps 方法
设置以前调用[IMetaDataEmit：:DefineTypeDef）](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)定义的类型的功能。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]从`mdTypeDef`原始调用[IMetaDataEmit 获得令牌：:DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。  
  
 `dwTypeDefFlags`  
 [在]`TypeDef`属性。 这是值的`CorTypeAttr`位掩码。  
  
 `tkExtends`  
 [在]基`mdToken`类的 。 从之前对[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)的调用中获取：:Define`null`导入类型，或 。  
  
 `rtkImplements[]`  
 [在]此类型实现的接口的令牌数组。 这些`mdTypeRef`令牌是使用[IMetaDataEmit：:Define 导入类型](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)获得的。 数组的最后一个元素必须是`mdTokenNil`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
