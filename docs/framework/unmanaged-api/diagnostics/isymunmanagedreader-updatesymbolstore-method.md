---
title: ISymUnmanagedReader::UpdateSymbolStore 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d84d4fccb2cb4e500f07f6bfbfb93b8c7b81f5d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939008"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>ISymUnmanagedReader::UpdateSymbolStore 方法
使用增量符号存储区更新现有的符号存储区。 此方法在 "编辑并继续" 方案中用于更新符号存储区, 以匹配原始可移植可执行 (PE) 文件的增量。  
  
> [!NOTE]
> 只需指定`filename`或`pIStream`参数之一, 而不能同时指定两者。 如果`filename`指定了, 则将用该文件中的符号更新符号存储区。 如果`pIStream`指定了, 则将用<xref:System.Runtime.InteropServices.ComTypes.IStream>中的数据更新存储区。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>参数  
 `filename`  
 中包含符号存储区的文件的名称。  
  
 `pIStream`  
 中文件流, 用作`filename`参数的替代项。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功, 则返回 S_OK;否则, E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym, CorSym  
  
## <a name="see-also"></a>请参阅

- [ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
