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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177268"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps 方法
获取由指定事件令牌表示的事件的元数据信息，包括声明类型、代理的添加和删除方法以及任何标志和其他关联数据。  
  
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
  
## <a name="parameters"></a>parameters  
 `ev`  
 [在]表示要获取其元数据的事件元数据令牌。  
  
 `pClass`  
 [出]指向表示声明事件的类的 TypeDef 令牌的指针。  
  
 `szEvent`  
 [出]引用`ev`的事件的名称。  
  
 `pchEvent`  
 [在]请求的长度以宽字符。 `szEvent`  
  
 `pdwEventFlags`  
 [出]返回的长度以宽字符。 `szEvent`  
  
 `ptkEventType`  
 [出]指向表示事件<xref:System.Delegate>类型的 TypeRef 或 TypeDef 元数据令牌的指针。  
  
 `pmdAddOn`  
 [出]指向元数据令牌的指针，表示为事件添加处理程序的方法。  
  
 `pmdRemoveOn`  
 [出]指向表示删除事件处理程序的方法的元数据令牌的指针。  
  
 `pmdFire`  
 [出]指向表示引发事件的方法的元数据令牌的指针。  
  
 `rmdOtherMethod`  
 [出]指向与事件关联的其他方法的令牌指针数组。  
  
 `cMax`  
 [in] `rmdOtherMethod` 数组的最大大小。  
  
 `pcOtherMethod`  
 [出]在 中`rmdOtherMethod`返回的令牌数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
