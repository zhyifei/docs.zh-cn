---
title: "ISymUnmanagedReader::Initialize 方法"
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
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 433cd62f7801d386f3b34b7fc8e95bd1d0c5f765
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize 方法
初始化此读取器将与，以及该模块的文件名称相关联的元数据导入程序接口的符号读取器。  
  
> [!NOTE]
>  此方法可以一次调用，必须在其他任何读取器方法之前调用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a>参数  
 `importer`  
 [in]此读取器将与之关联的元数据导入程序接口。  
  
 `filename`  
 [in]模块的文件名称。 你可以使用`pIStream`参数相反。  
  
 `searchPath`  
 [in]要搜索的路径。 此参数可选。  
  
 `pIStream`  
 [in]文件流用作 filename 参数的替代方法。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="remarks"></a>备注  
 你需要只能指定其中一个`filename`或`pIStream`参数，不是两个。 `searchPath` 参数是可选的。  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
