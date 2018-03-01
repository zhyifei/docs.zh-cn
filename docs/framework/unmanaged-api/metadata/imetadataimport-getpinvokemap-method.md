---
title: "IMetaDataImport::GetPinvokeMap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a28d628040a35d309515703563239a5f802dc4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetpinvokemap-method"></a>IMetaDataImport::GetPinvokeMap 方法
获取用于表示 PInvoke 调用的目标程序集的 ModuleRef 标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
#### <a name="parameters"></a>参数  
 `tk`  
 [in]要获取的 PInvoke 映射元数据的 FieldDef 或 MethodDef 标记。  
  
 `pdwMappingFlags`  
 [out]指向用于映射的标志的指针。 此值是从一个位掩码[CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md)枚举。  
  
 `szImportName`  
 [out]非托管目标 DLL 的名称。  
  
 `cchImportName`  
 [in]在宽字符为单位的大小`szImportName`。  
  
 `pchImportName`  
 [out]在中返回的宽字符数`szImportName`。  
  
 `pmrImportDLL`  
 [out]指向表示非托管的目标对象库的 ModuleRef 标记的指针。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
