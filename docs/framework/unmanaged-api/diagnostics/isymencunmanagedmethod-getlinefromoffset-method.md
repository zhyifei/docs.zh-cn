---
title: "ISymENCUnmanagedMethod::GetLineFromOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetLineFromOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2f18357b3a58a5409da93d4d2491997e9ca1cc70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset 方法
获取与某一偏移量关联的行信息。 如果偏移量的参数 (`dwOffset`) 不是序列点，此方法获取与前一个偏移量关联的行信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
#### <a name="parameters"></a>参数  
 `dwOffset`  
 [in]A`ULONG32`包含的偏移量。  
  
 `pline`  
 [out]指向的指针`ULONG32`接收行。  
  
 `pcolumn`  
 [out]指向的指针`ULONG32`接收列。  
  
 `pendLine`  
 [out]指向的指针`ULONG32`接收结束行。  
  
 `pendColumn`  
 [out]指向的指针`ULONG32`接收的结束列。  
  
 `pdwStartOffset`  
 [out]指向的指针`ULONG32`接收相关联的序列点。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>另请参阅  
 [ISymENCUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
