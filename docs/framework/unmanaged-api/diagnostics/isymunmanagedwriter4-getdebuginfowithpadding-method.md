---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d669ae15c01a560f2cefb6e361ca32411652fbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732968"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a>ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法
功能一样[GetDebugInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)只不过用终止的 null 字符，以使的固定的大小的字符串数据后面的零填充的路径字符串`MAX_PATH`。 填充仅有自身的路径字符串长度是否小于`MAX_PATH`。  
  
 这使得更轻松地编写该差异 PE 文件的工具。  
  
## <a name="syntax"></a>语法  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a>返回值  
 返回 `HRESULT`。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅
- [ISymUnmanagedWriter4 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
