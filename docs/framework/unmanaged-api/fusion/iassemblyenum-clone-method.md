---
title: IAssemblyEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::Clone
helpviewer_keywords:
- Clone method, IAssemblyEnum interface [.NET Framework fusion]
- IAssemblyEnum::Clone method [.NET Framework fusion]
ms.assetid: 0014bb66-590c-486c-9ade-f2133905cd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d288f4ccf91567224546df1a3309a411590a5a12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779025"
---
# <a name="iassemblyenumclone-method"></a>IAssemblyEnum::Clone 方法
创建的浅表副本[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppEnum`  
 [out]指向该副本的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IAssemblyEnum 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
