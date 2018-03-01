---
title: "ISymUnmanagedENCUpdate::UpdateSymbolStore2 方法"
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
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a366047530f3433ab1bfbb5f30d4b9b54c5bdb08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>ISymUnmanagedENCUpdate::UpdateSymbolStore2 方法
允许编译器忽略未修改的程序数据库 (PDB) 流中的函数，提供行信息满足的要求。 可使用旧的 PDB 行信息以及该函数中的所有行的一个增量确定正确的行信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a>参数  
 `pIStream`  
 [in]指向的指针<xref:IStream>包含行信息。  
  
 `pDeltaLines`  
 [in]指向的指针[SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md)结构，其中包含已更改的行。  
  
 `cDeltaLines`  
 [in]A `ULONG` ，它表示已更改的行数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedENCUpdate 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
