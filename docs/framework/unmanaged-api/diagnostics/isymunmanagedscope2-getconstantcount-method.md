---
title: "ISymUnmanagedScope2::GetConstantCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2.GetConstantCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 26ce28c3542af80f033cc765c3e462a34e4fb3e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscope2getconstantcount-method"></a>ISymUnmanagedScope2::GetConstantCount 方法
获取此范围内定义的常量的计数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]指向的指针`ULONG32`接收大小，以字符为单位，包含常量所需的缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>另请参阅  
 [ISymUnmanagedScope2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
