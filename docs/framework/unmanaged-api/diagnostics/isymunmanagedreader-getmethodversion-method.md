---
title: ISymUnmanagedReader::GetMethodVersion 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 45aaceb2c39703cb1369941ce801c9cff1935ad6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555838"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a>ISymUnmanagedReader::GetMethodVersion 方法
获取方法版本。 方法版本从 1 开始，在每的次递增的方法重新编译。 重新编译可发生该方法无需进行更改。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a>参数  
 `pMethod`  
 [in]要为其获取版本方法。  
  
 `version`  
 [out]指向一个变量来接收方法版本的指针。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅
- [ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
