---
title: ISymUnmanagedWriter5 接口
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: 18371b6aefb002f5adf27d43f85194c6c35f6ef5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121642"
---
# <a name="isymunmanagedwriter5-interface"></a>ISymUnmanagedWriter5 接口
ISymUnmanagedWriter5 接口。  
  
## <a name="syntax"></a>语法  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a>方法  
 此接口包含下列方法：  
  
|方法|描述|  
|------------|-----------------|  
|[CloseMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|关闭 "特定自定义数据" 部分以获取令牌到源范围的映射信息。 关闭后，不能再添加映射信息。|  
|[MapTokenToSourceSpan 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|将给定的元数据标记映射到指定源文件中的给定源行范围。<br /><br /> 必须在对[OpenMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)和[CloseMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)的调用之间调用。|  
|[OpenMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|打开一个特殊的自定义数据部分，将令牌到源范围的映射信息发送到。 如果方法已打开（或相反），则打开此节是错误的。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>请参阅

- [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter4 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
