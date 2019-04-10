---
title: IMetaDataImport::GetClassLayout 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11748d3ad99c4050045cce3786eec5604c02ac0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197797"
---
# <a name="imetadataimportgetclasslayout-method"></a>IMetaDataImport::GetClassLayout 方法
获取指定的 TypeDef 标记所引用类的布局信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a>参数  
 `td`  
 [in]具有要返回的布局的类的 TypeDef 标记。  
  
 `pdwPackSize`  
 [out]值 1、 2、 4、 8 或 16，它表示类的包大小之一。  
  
 `rFieldOffset`  
 [out]一个数组[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)值。  
  
 `cMax`  
 [in] `rFieldOffset` 数组的最大大小。  
  
 `pcFieldOffset`  
 [out]在返回的元素数目`rFieldOffset`。  
  
 `pulClassSize`  
 [out]以字节为单位表示的类的大小`td`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 包含为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
