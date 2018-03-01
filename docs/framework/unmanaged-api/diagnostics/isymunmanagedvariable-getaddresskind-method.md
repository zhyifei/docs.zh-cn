---
title: "ISymUnmanagedVariable::GetAddressKind 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5c4651641e3c430379b11698acf29eae450b02b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a>ISymUnmanagedVariable::GetAddressKind 方法
获取此变量的地址的种类。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]指向的指针`ULONG32`接收的值。 可能的值定义在[CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md)枚举。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedVariable 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
