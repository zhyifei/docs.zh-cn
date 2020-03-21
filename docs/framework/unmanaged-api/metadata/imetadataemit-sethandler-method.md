---
title: IMetaDataEmit::SetHandler 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177544"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler 方法
将指定`IUnknown`指针引用的方法集为令牌重映射的通知回调。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>parameters  
 `pUnk`  
 [在]要注册的处理程序。  
  
## <a name="remarks"></a>备注  
 元数据引擎使用 提供`SetHandler`的方法向未以优化方式生成记录并希望优化保存的记录的编译器发送通知。  
  
 如果未通过`SetHandler`提供回调方法，则不会对保存执行优化，除非每个作用域在合并`IMapToken`时合并了多个导入作用域。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
