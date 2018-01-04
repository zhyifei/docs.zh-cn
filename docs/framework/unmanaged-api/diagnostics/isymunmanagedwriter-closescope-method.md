---
title: "ISymUnmanagedWriter::CloseScope 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d47be1d220729ed32fcf77a77e611003085c15d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a>ISymUnmanagedWriter::CloseScope 方法
关闭当前词法范围。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a>参数  
 `endOffset`  
 [in]从位于词法作用域，以字节为单位中的最后一个指令的末尾的点方法的开头的偏移量。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="remarks"></a>备注  
 一旦关闭作用域时，可以在其中定义没有更多的变量。  
  
 [Isymunmanagedwriter:: Openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)返回可以用于一个不透明的作用域标识符[isymunmanagedwriter:: Setscoperange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)以更高版本定义的作用域的起始和结束偏移量。 在这种情况下，忽略传递到 `ISymUnmanagedWriter::OpenScope` 和 `ISymUnmanagedWriter::CloseScope` 的偏移量。 范围标识符是仅在当前方法中有效。  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
