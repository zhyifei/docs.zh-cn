---
title: IMetaDataImport::EnumCustomAttributes 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b549c6eacad63b165d26c203817f1a2adac57bca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448633"
---
# <a name="imetadataimportenumcustomattributes-method"></a>IMetaDataImport::EnumCustomAttributes 方法
枚举与指定的类型或成员相关联的自定义特性定义标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a>参数  
 `phEnum`  
 [在中，out]返回的枚举数指向的指针。  
  
 `tk`  
 [in]用于枚举，则为零的所有自定义属性的作用域的令牌。  
  
 `tkType`  
 [in]要枚举的属性的类型的构造函数的令牌或`null`对于所有类型。  
  
 `rCustomAttributes`  
 [out]自定义特性标记的数组。  
  
 `cMax`  
 [in] `rCustomAttributes` 数组的最大大小。  
  
 `pcCustomAttributes`  
 [out，optional]在中返回的令牌值的实际数目`rCustomAttributes`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` 已成功返回。|  
|`S_FALSE`|没有自定义属性来枚举。 在这种情况下，`pcCustomAttributes`为零。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
