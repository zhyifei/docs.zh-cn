---
title: ISymUnmanagedDocument::GetCheckSumAlgorithmId 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
ms.openlocfilehash: 2bc673d2e331cd32d5317cb20f9418eb3a3b144a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431064"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a>ISymUnmanagedDocument::GetCheckSumAlgorithmId 方法
如果没有校验和，则获取校验和算法标识符，或返回所有零的 GUID。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a>参数  
 `pRetVal`  
 弄指向接收校验和算法标识符的变量的指针。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则 S_OK。  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedDocument 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
