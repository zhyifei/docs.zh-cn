---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f20039318d6e1230ccc0fbd203fc44686806bb2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604465"
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
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅
- [ISymUnmanagedAsyncMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
