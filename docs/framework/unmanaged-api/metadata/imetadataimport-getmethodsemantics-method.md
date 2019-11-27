---
title: IMetaDataImport::GetMethodSemantics 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: 0542c518b64764ad27aa00b8d595be1191059436
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437456"
---
# <a name="imetadataimportgetmethodsemantics-method"></a>IMetaDataImport::GetMethodSemantics 方法
获取指示指定的 MethodDef 标记所引用的方法与指定的 EventProp 标记所引用的成对属性和事件之间的关系的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `mb`  
 中一个 MethodDef 标记，表示要获取其语义角色信息的方法。  
  
 `tkEventProp`  
 中一个标记，它表示要为其获取方法的角色的成对属性和事件。  
  
 `pdwSemanticsFlags`  
 弄指向关联语义标志的指针。 此值是[CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md)枚举中的位掩码。  
  
## <a name="remarks"></a>备注  
 [IMetaDataEmit：:D efineproperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)方法设置方法的语义标志。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
