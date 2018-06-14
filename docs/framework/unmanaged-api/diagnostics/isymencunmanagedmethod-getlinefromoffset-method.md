---
title: ISymENCUnmanagedMethod::GetLineFromOffset 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29990ad6a94f063577236bdbc84d02d4d2b4b2f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426128"
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
  
## <a name="see-also"></a>请参阅  
 [ISymENCUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
