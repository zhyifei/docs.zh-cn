---
title: IMetaDataImport::EnumMethodSemantics 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175455"
---
# <a name="imetadataimportenummethodsemantics-method"></a>IMetaDataImport::EnumMethodSemantics 方法
枚举与指定方法相关的属性和属性更改事件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a>parameters  
 `phEnum`  
 [进出]指向枚举器的指针。 对于此方法的第一次调用，这必须为 NULL。  
  
 `mb`  
 [在]限制枚举范围的 MethodDef 令牌。  
  
 `rEventProp`  
 [出]用于存储事件或属性的数组。  
  
 `cMax`  
 [in] `rEventProp` 数组的最大大小。  
  
 `pcEventProp`  
 [出]在 中`rEventProp`返回的事件或属性数。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics`已成功返回。|  
|`S_FALSE`|没有要枚举的事件或属性。 在这种情况下，`pcEventProp`为零。|  
  
## <a name="remarks"></a>备注  
 许多通用语言运行时类型定义与其属性相关的*属性*`Changed`事件和`On`*属性*`Changed`方法。 例如，<xref:System.Windows.Forms.Control?displayProperty=nameWithType>类型定义<xref:System.Windows.Forms.Control.Font%2A>属性、<xref:System.Windows.Forms.Control.FontChanged>事件和方法。 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 属性调用<xref:System.Windows.Forms.Control.Font%2A><xref:System.Windows.Forms.Control.OnFontChanged%2A>方法的集访问器方法，该方法反过来引发事件<xref:System.Windows.Forms.Control.FontChanged>。 您将使用`EnumMethodSemantics`MethodDef 调用，<xref:System.Windows.Forms.Control.OnFontChanged%2A>以获得对<xref:System.Windows.Forms.Control.Font%2A>属性和<xref:System.Windows.Forms.Control.FontChanged>事件的引用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
