---
title: IMetaDataImport::GetRVA 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 190bcacc84646cfd9294cf2b6b53b0474f38758f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177218"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA 方法
获取由指定令牌表示的方法或字段的相对虚拟地址 （RVA） 和实现标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>parameters  
 `tk`  
 [在]表示要返回 RVA 的代码对象的 MethodDef 或 FieldDef 元数据令牌。 如果令牌是 FieldDef，则该字段必须是全局变量。  
  
 `pulCodeRVA`  
 [出]指向令牌表示的代码对象的相对虚拟地址的指针。  
  
 `pdwImplFlags`  
 [出]指向方法的实现标志的指针。 此值是[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举中的位掩码。 仅当 是`pdwImplFlags`MethodDef`tk`令牌时，值才有效。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
