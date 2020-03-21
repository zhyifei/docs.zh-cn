---
title: IMetaDataImport2::EnumMethodSpecs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 2df53ba53c64e042abc54a1d2ac043d301acdde9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177175"
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs 方法
获取与指定方法Def或会员Ref令牌关联的 MethodSpec 令牌数组的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a>parameters  
 `phEnum`  
 [进出]指向 的枚举器的`rMethodSpecs`指针。  
  
 `tk`  
 [在]代表其方法Spec令牌的方法的会员Ref或 MethodDef 令牌。 如果 值`tk`为 0（零），则将枚举作用域中的所有 MethodSpec 令牌。  
  
 `rMethodSpecs`  
 [出]要枚举的 MethodSpec 令牌的数组。  
  
 `cMax`  
 [在]要放置在 中`rMethodSpecs`的最大令牌数。  
  
 `pcMethodSpecs`  
 [出]放置在 的`rMethodSpecs`返回的令牌数。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs`已成功返回。|  
|`S_FALSE`|`phEnum`没有成员元素。 在这种情况下，`pcMethodSpecs`设置为 0（零）。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
