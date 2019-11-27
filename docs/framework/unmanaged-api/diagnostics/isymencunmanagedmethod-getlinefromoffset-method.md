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
ms.openlocfilehash: 94a571a4bc01b805387aebe5a6e23bad0b735313
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448650"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset 方法
获取与偏移量关联的行信息。 如果 offset 参数（`dwOffset`）不是序列点，则此方法将获取与上一个偏移量关联的行信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>参数  
 `dwOffset`  
 中一个包含偏移量的 `ULONG32`。  
  
 `pline`  
 弄指向接收行的 `ULONG32` 的指针。  
  
 `pcolumn`  
 弄指向接收列的 `ULONG32` 的指针。  
  
 `pendLine`  
 弄指向接收结束行的 `ULONG32` 的指针。  
  
 `pendColumn`  
 弄指向接收结束列的 `ULONG32` 的指针。  
  
 `pdwStartOffset`  
 弄指向接收关联序列点的 `ULONG32` 的指针。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [ISymENCUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
