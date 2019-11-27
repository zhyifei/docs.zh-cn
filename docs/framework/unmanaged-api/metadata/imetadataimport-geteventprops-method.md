---
title: IMetaDataImport::GetEventProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 18fe0c834506d0ac4cd15fd7af4c4f15904b0f81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437584"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps 方法
获取指定事件标记所表示的事件的元数据信息，包括声明类型、委托的添加和移除方法以及任何标志和其他关联的数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a>参数  
 `ev`  
 中表示要获取其元数据的事件的事件元数据标记。  
  
 `pClass`  
 弄一个指针，指向表示声明事件的类的 TypeDef 标记。  
  
 `szEvent`  
 弄`ev`引用的事件的名称。  
  
 `pchEvent`  
 中请求的长度（以宽字符为 `szEvent`）。  
  
 `pdwEventFlags`  
 弄`szEvent`的宽字符中返回的长度。  
  
 `ptkEventType`  
 弄指向表示事件的 <xref:System.Delegate> 类型的 TypeRef 或 TypeDef 元数据标记的指针。  
  
 `pmdAddOn`  
 弄指向表示添加事件处理程序的方法的元数据标记的指针。  
  
 `pmdRemoveOn`  
 弄指向表示删除事件处理程序的方法的元数据标记的指针。  
  
 `pmdFire`  
 弄指向表示引发事件的方法的元数据标记的指针。  
  
 `rmdOtherMethod`  
 弄指向与事件关联的其他方法的标记指针的数组。  
  
 `cMax`  
 [in] `rmdOtherMethod` 数组的最大大小。  
  
 `pcOtherMethod`  
 弄`rmdOtherMethod`中返回的令牌数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
