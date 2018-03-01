---
title: "LoadTypeLibWithResolver 函数"
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
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f069d09f25575c39db097024384ad1bf14eaaf02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="loadtypelibwithresolver-function"></a>LoadTypeLibWithResolver 函数
加载类型库中并使用所提供[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)若要解决任何内部引用的类型库。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a>参数  
 `szFile`  
 [in]类型库文件路径。  
  
 `regkind`  
 [in]A [REGKIND 枚举](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx)控制如何注册类型库的标志。 其可能的值有：  
  
-   `REGKIND_DEFAULT`： 使用默认注册行为。  
  
-   `REGKIND_REGISTER`： 注册此类型库。  
  
-   `REGKIND_NONE`： 请勿注册此类型库。  
  
 `pTlbResolver`  
 [in]指向的实现的[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)。  
  
 `pptlib`  
 [out]对正在加载的类型库的引用。  
  
## <a name="return-value"></a>返回值  
 下表中列出的 HRESULT 值之一。  
  
|返回值|含义|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_OUTOFMEMORY`|内存不足。|  
|`E_POINTER`|一个或多个指针均无效。|  
|`E_INVALIDARG`|无效的一个或多个参数。|  
|`TYPE_E_IOERROR`|函数无法写入到文件中。|  
|`TYPE_E_REGISTRYACCESS`|无法打开系统注册数据库。|  
|`TYPE_E_INVALIDSTATE`|无法打开类型库。|  
|`TYPE_E_CANTLOADLIBRARY`|无法加载类型库或 DLL。|  
  
## <a name="remarks"></a>备注  
 [Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)调用`LoadTypeLibWithResolver`在程序集到类型库转换过程中的函数。  
  
 此函数将加载指定的类型库具有对注册表的最低访问权限。 然后，该函数将检查内部引用的类型库，其中每个必须加载和添加到父类型库的类型库。  
  
 可以加载引用的类型库之前，其引用文件路径必须解析为完整文件路径。 这通过实现[ResolveTypeLib 方法](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md)由提供[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)，后者在传递`pTlbResolver`参数。  
  
 当已知的引用的类型库的完整文件路径时，`LoadTypeLibWithResolver`函数加载，并将引用的类型库添加到父类型库中，创建合并的主类型库。  
  
 该函数解析并加载了所有内部引用的类型库后，它将返回到主解析的类型库中的引用`pptlib`参数。  
  
 `LoadTypeLibWithResolver`函数通常由[Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)，其中提供其自身内部[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)中的实现`pTlbResolver`参数。  
  
 如果调用`LoadTypeLibWithResolver`直接，则必须提供你自己[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)实现。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** TlbRef.h  
  
 **库：** TlbRef.lib  
  
 **.NET framework 版本：** 3.5、 3.0、 2.0  
  
## <a name="see-also"></a>请参阅  
 [Tlbexp Helper 函数](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx 函数](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)
