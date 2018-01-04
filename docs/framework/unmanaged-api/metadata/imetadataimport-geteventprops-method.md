---
title: "IMetaDataImport::GetEventProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetEventProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73f257c46fd21355eeaabbe9e1b5d2841d2c3911
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps 方法
获取表示指定的事件标记，包括声明类型、 添加和删除方法的委托，任何标志及其他关联的数据的事件的元数据信息。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `ev`  
 [in]表示要获取的元数据的事件的事件元数据标记。  
  
 `pClass`  
 [out]指向表示声明该事件的类的 TypeDef 标记的指针。  
  
 `szEvent`  
 [out]引用的事件的名称`ev`。  
  
 `pchEvent`  
 [in]请求的长度以宽字符为单位`szEvent`。  
  
 `pdwEventFlags`  
 [out]返回的长度以宽字符为单位`szEvent`。  
  
 `ptkEventType`  
 [out]一个指向 TypeRef 或 TypeDef 元数据令牌表示<xref:System.Delegate>事件类型。  
  
 `pmdAddOn`  
 [out]指向表示添加的处理程序事件的方法的元数据标记的指针。  
  
 `pmdRemoveOn`  
 [out]指向表示中移除事件处理程序的方法的元数据标记的指针。  
  
 `pmdFire`  
 [out]指向表示引发事件的方法的元数据标记的指针。  
  
 `rmdOtherMethod`  
 [out]与其他方法与事件关联的令牌指针的数组。  
  
 `cMax`  
 [in] `rmdOtherMethod` 数组的最大大小。  
  
 `pcOtherMethod`  
 [out]在中返回的令牌数`rmdOtherMethod`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
