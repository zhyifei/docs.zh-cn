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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8cd086a86d104fdfebf1a8298a22b795cb2389b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782648"
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs 方法
获取可枚举数组 MethodSpec 与关联的标记指定的 MethodDef 或 MemberRef 令牌。  
  
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
  
## <a name="parameters"></a>参数  
 `phEnum`  
 [in、 out]指向的枚举器的`rMethodSpecs`。  
  
 `tk`  
 [in]新对象或 MemberRef 令牌，表示其 MethodSpec 令牌是要枚举的方法。 如果的值`tk`为 0 （零），则将枚举所有 MethodSpec 令牌的作用域中。  
  
 `rMethodSpecs`  
 [out]要枚举的 MethodSpec 标记的数组。  
  
 `cMax`  
 [in]要放置在中的令牌的请求最大数目`rMethodSpecs`。  
  
 `pcMethodSpecs`  
 [out]返回的标记数置于`rMethodSpecs`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` 已成功返回。|  
|`S_FALSE`|`phEnum` 不包含任何成员元素。 在这种情况下，`pcMethodSpecs`设置为 0 （零）。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
