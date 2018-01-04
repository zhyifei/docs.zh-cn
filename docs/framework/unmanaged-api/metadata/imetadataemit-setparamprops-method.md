---
title: "IMetaDataEmit::SetParamProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8ada9deddf8528321797c1f9bd06b5b775ac4bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetparamprops-method"></a>IMetaDataEmit::SetParamProps 方法
设置或更改功能的已定义的调用的方法参数[imetadataemit:: Defineparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a>参数  
 `pd`  
 [in]目标参数的标记。  
  
 `szName`  
 [in]以 Unicode 参数的名称。  
  
 `dwParamFlags`  
 [in]参数的标志。  
  
 `dwCPlusTypeFlag`  
 [in]ELEMENT_TYPE_ * 的常量值。  
  
 `pValue`  
 [in]参数的常量值。  
  
 `cchValue`  
 [in]以 (Unicode) 字符为单位的大小`pValue`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
