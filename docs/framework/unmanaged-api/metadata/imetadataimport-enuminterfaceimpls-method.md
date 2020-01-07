---
title: IMetaDataImport::EnumInterfaceImpls 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338055"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls 方法
枚举由指定 `TypeDef`实现的所有接口。 
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>参数  
 `phEnum`  
 [in，out]指向枚举器的指针。  
  
 `td`  
 中要枚举其 MethodDef 标记表示接口实现的 TypeDef 的标记。  
  
 `rImpls`  
 弄用于存储 MethodDef 标记的数组。  
  
 `cMax`  
 中`rImpls` 数组的最大长度。  
  
 `pcImpls`  
 弄`rImpls`中返回的标记的实际数量。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` 成功返回。|  
|`S_FALSE`|没有要枚举的 MethodDef 标记。 在这种情况下，`pcImpls` 设置为零。|  

## <a name="remarks"></a>备注

枚举为指定的 `TypeDef`实现的每个接口返回 `mdInterfaceImpl` 标记的集合。 接口令牌按指定的顺序（通过 `DefineTypeDef` 或 `SetTypeDefProps`）返回。 可以使用[GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)查询返回 `mdInterfaceImpl` 标记的属性。
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
