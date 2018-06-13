---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efa34d262157faed2e05cd6e7517c259cd279146
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428571"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a>ISymUnmanagedReader2::GetMethodByVersionPreRemap 方法
获取符号读取器方法，在给定方法标记和编辑并继续的版本号。 版本号从 1 开始，并递增的编辑并继续操作后更改此方法每次。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a>参数  
 `token`  
 [in]方法的元数据标记。  
  
 `version`  
 [in]方法版本中。  
  
 `pRetVal`  
 [out]指向返回的指针[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)接口。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl。 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedReader2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
