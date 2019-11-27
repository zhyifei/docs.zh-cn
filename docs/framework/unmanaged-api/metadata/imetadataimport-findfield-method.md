---
title: IMetaDataImport::FindField 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 842d6c0deb90bc45cb59454fb30fcc3544d742f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437951"
---
# <a name="imetadataimportfindfield-method"></a>IMetaDataImport::FindField 方法
获取一个指针，该指针指向由指定 <xref:System.Type> 包围且具有指定名称和元数据签名的字段的 FieldDef 标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a>参数  
 `td`  
 中包含要搜索的字段的类或接口的 TypeDef 标记。 如果 `mdTokenNil`此值，则将对全局变量执行查找。  
  
 `szName`  
 中要搜索的字段的名称。  
  
 `pvSigBlob`  
 中指向字段的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 中`pvSigBlob`的大小（以字节为单位）。  
  
 `pmb`  
 弄指向匹配的 FieldDef 标记的指针。  
  
## <a name="remarks"></a>备注  
 您可以使用其封闭类或接口（`td`）、其名称（`szName`）以及（可选）签名（`pvSigBlob`）来指定字段。  
  
 传递给 `FindField` 的签名必须已在当前范围内生成，因为签名将绑定到特定范围。 签名可以嵌入标识封闭类或值类型的标记。 （标记是本地 TypeDef 表中的索引）。 不能在当前范围的上下文之外生成运行时签名，并使用该签名作为 `FindField`的输入。  
  
 `FindField` 仅查找直接在类或接口中定义的字段;它不会找到继承的字段。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
