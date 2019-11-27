---
title: ISymUnmanagedWriter::GetDebugInfo 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
ms.openlocfilehash: 2b901a3dac499f1ce3f843c59122dd8fd5022147
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427959"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>ISymUnmanagedWriter::GetDebugInfo 方法
返回编译器编写可移植可执行（PE）文件头中的调试目录条目所需的信息。 符号编写器填写除 `TimeDateStamp` 和 `PointerToRawData`之外的所有字段。 （编译器负责正确设置这两个字段。）  
  
 编译器应调用此方法，将数据 blob 发出到 PE 文件，将 IMAGE_DEBUG_DIRECTORY 中的 `PointerToRawData` 字段设置为指向发出的数据，并将 IMAGE_DEBUG_DIRECTORY 写入 PE 文件。 编译器还应将 `TimeDateStamp` 字段设置为等于正在生成的 PE 文件的 `TimeDateStamp`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>参数  
 `pIDD`  
 [in，out]指向符号编写器将填写的 IMAGE_DEBUG_DIRECTORY 的指针。  
  
 `cData`  
 中包含调试数据大小的 `DWORD`。  
  
 `pcData`  
 弄指向 `DWORD` 的指针，该指针接收包含调试数据所需的缓冲区大小。  
  
 `data`  
 弄指向缓冲区的指针，该缓冲区足以容纳符号存储区的调试数据。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
