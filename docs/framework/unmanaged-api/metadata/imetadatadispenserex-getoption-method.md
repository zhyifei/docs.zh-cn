---
title: IMetaDataDispenserEx::GetOption 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177718"
---
# <a name="imetadatadispenserexgetoption-method"></a>IMetaDataDispenserEx::GetOption 方法
获取当前元数据作用域的指定选项的值。 该选项控制如何处理对当前元数据作用域的调用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a>parameters  
 `optionId`  
 [在]指向 GUID 的指针，用于指定要检索的选项。 有关支持的 GUID 的列表，请参阅备注部分。  
  
 `pValue`  
 [出]返回的选项的值。 此值的类型将是指定选项类型的变体。  
  
## <a name="remarks"></a>备注  
 下面的列表显示了此方法支持的 GUID。 有关说明，请参阅[IMetaDataDispenserEx：：SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)方法。 如果`optionId`不在此列表中，此方法将返回 HRESULT `E_INVALIDARG`，指示不正确的参数。  
  
- 元数据检查重复项  
  
- 元数据参考检查  
  
- 元数据通知令牌移动  
  
- 元数据集  
  
- 元数据错误，如果已发出命令  
  
- 元数据生成适配器  
  
- 元数据链接器选项  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
