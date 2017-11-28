---
title: "ISymUnmanagedAsyncMethod::GetKickoffMethod 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e017097183243c84a2ce40cc473067e05c80c3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a>ISymUnmanagedAsyncMethod::GetKickoffMethod 方法
请参阅[DefineKickoffMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)。  
  
## <a name="syntax"></a>语法  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a>返回值  
 返回 `HRESULT`。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>另请参阅  
 [ISymUnmanagedAsyncMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
