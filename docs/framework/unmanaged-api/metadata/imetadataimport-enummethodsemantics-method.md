---
title: "IMetaDataImport::EnumMethodSemantics 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d5ec79701f73b8beb7759d72b972fc347a339c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethodsemantics-method"></a>IMetaDataImport::EnumMethodSemantics 方法
枚举与指定方法相关的属性和属性更改事件。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a>参数  
 `phEnum`  
 [在中，out]枚举数指向的指针。 这必须在首次调用此方法为 NULL。  
  
 `mb`  
 [in]限制在枚举的作用域的 MethodDef 标记。  
  
 `rEventProp`  
 [out]用于存储事件或属性的数组。  
  
 `cMax`  
 [in] `rEventProp` 数组的最大大小。  
  
 `pcEventProp`  
 [out]事件或属性中返回的数`rEventProp`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics`已成功返回。|  
|`S_FALSE`|没有任何事件或属性，以枚举。 在这种情况下，`pcEventProp`为零。|  
  
## <a name="remarks"></a>备注  
 许多公共语言运行时类型定义*属性*`Changed`事件和`On`*属性*`Changed`其属性与相关方法。 例如，<xref:System.Windows.Forms.Control?displayProperty=nameWithType>类型定义<xref:System.Windows.Forms.Control.Font%2A>属性，<xref:System.Windows.Forms.Control.FontChanged>事件，和<xref:System.Windows.Forms.Control.OnFontChanged%2A>方法。 Set 访问器方法的<xref:System.Windows.Forms.Control.Font%2A>属性调用<xref:System.Windows.Forms.Control.OnFontChanged%2A>方法，该方法引发<xref:System.Windows.Forms.Control.FontChanged>事件。 你应该调用`EnumMethodSemantics`使用为 MethodDef<xref:System.Windows.Forms.Control.OnFontChanged%2A>若要获取对引用<xref:System.Windows.Forms.Control.Font%2A>属性和<xref:System.Windows.Forms.Control.FontChanged>事件。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
