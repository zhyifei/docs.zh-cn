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
ms.openlocfilehash: 5c81bc82e19bce658336e4860a61f2721e17423d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431688"
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam 方法
创建具有指定标记所引用的方法的指定签名的参数定义，并获取该参数定义的标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `md`  
 中正在定义其参数的方法的标记。  
  
 `ulParamSeq`  
 中参数序列号。  
  
 `szName`  
 中Unicode 中参数的名称。  
  
 `dwParamFlags`  
 中参数的标志。 这是 `CorParamAttr` 值的位掩码。  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_`常量值的 *\** 。  
  
 `pValue`  
 中参数的常数值。  
  
 `cchValue`  
 中`pValue`的大小（以 Unicode 字符为格式）。  
  
 `ppd`  
 弄分配 `mdParamDef` 标记。  
  
## <a name="remarks"></a>备注  
 对于参数，`ulParamSeq` 中的序列值从1开始。 返回值的序列号为0。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
