---
title: ISymUnmanagedWriter::Initialize2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
ms.openlocfilehash: 041df959139a0be77f40d6aa5655ff15f93fb26f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427942"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>ISymUnmanagedWriter::Initialize2 方法
设置此编写器将与之关联的元数据发射器接口，并设置调试符号将写入的输出文件名。 此方法还允许您设置程序数据库（PDB）文件的最终位置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>参数  
 `emitter`  
 中指向元数据发射器接口的指针。  
  
 `tempfilename`  
 中指向 `WCHAR` 的指针，该指针包含将调试符号写入到的文件名。 如果为不使用文件名的编写器指定文件名，则忽略此参数。  
  
 `pIStream`  
 中如果已指定，则符号编写器会将符号发送到给定的 <xref:System.Runtime.InteropServices.ComTypes.IStream>，而不是发送到 `filename` 参数中指定的文件。 `pIStream` 参数是可选的。  
  
 `fFullBuild`  
 [in] 如果这是完全重新生成，则 `true`;如果这是增量编译，则 `false`。  
  
 `finalfilename`  
 中指向作为 PDB 文件最终位置路径字符串的 `WCHAR` 的指针。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Initialize 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
