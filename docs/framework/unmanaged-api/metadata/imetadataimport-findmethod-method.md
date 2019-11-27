---
title: IMetaDataImport::FindMethod 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 470b6511366cef1680eaf97f9ab376736add55c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437895"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod 方法
获取一个指针，该指针指向方法的 MethodDef 标记，该方法由指定的 <xref:System.Type> 包含并且具有指定的名称和元数据签名。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>参数  
 `td`  
 中包含要搜索的成员的类型（类或接口）的 `mdTypeDef` 标记。 如果 `mdTokenNil`此值，则会对全局函数执行查找。  
  
 `szName`  
 中要搜索的方法的名称。  
  
 `pvSigBlob`  
 中指向方法的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 中`pvSigBlob`的大小（以字节为单位）。  
  
 `pmb`  
 弄指向匹配 MethodDef 标记的指针。  
  
## <a name="remarks"></a>备注  
 使用方法的封闭类或接口（`td`）、其名称（`szName`）以及可选的签名（`pvSigBlob`）来指定方法。 类或接口中可能有多个具有相同名称的方法。 在这种情况下，传递该方法的签名以查找唯一匹配项。  
  
 传递给 `FindMethod` 的签名必须已在当前范围内生成，因为签名将绑定到特定范围。 签名可以嵌入标识封闭类或值类型的标记。 该令牌是本地 TypeDef 表中的索引。 不能在当前范围的上下文之外生成运行时签名，并使用该签名作为输入 `FindMethod`。  
  
 `FindMethod` 仅查找直接在类或接口中定义的方法;它找不到继承的方法。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
