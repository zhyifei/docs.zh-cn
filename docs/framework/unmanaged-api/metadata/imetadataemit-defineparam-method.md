---
title: IMetaDataEmit::DefineParam 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d49ac70aceb76f69711ea4bf514f69697ac156c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam 方法
使用指定的签名与指定标记引用的方法创建的参数定义并获取该参数定义的标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a>参数  
 `md`  
 [in]正在定义中其参数的方法的标记。  
  
 `ulParamSeq`  
 [in]参数序列号。  
  
 `szName`  
 [in]以 Unicode 参数的名称。  
  
 `dwParamFlags`  
 [in]参数的的标志。 这是一个位掩码的`CorParamAttr`值。  
  
 `dwCPlusTypeFlag`  
 [in]`ELEMENT_TYPE_` *\** 的常量值。  
  
 `pValue`  
 [in]参数的常量值。  
  
 `cchValue`  
 [in]大小，以 Unicode 字符的`pValue`。  
  
 `ppd`  
 [out]`mdParamDef`分配的令牌。  
  
## <a name="remarks"></a>备注  
 序列值在`ulParamSeq`开头的参数 1。 返回值具有序列号为 0。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
