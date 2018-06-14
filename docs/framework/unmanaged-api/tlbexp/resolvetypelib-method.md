---
title: ResolveTypeLib 方法
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96a9672ee05cb1fe2573620bd1dea23e57339c93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460836"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib 方法
通过返回其完全限定的路径来解析类型库的简单名称。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a>参数  
 `bstrSimpleName`  
 [in]A [BSTR](http://msdn.microsoft.com/library/1b2d7d2c-47af-4389-a6b6-b01b7e915228)包含类型库的简单名称。  
  
 `tlbid`  
 [in]分配给在注册表中的类型库的 GUID。  
  
 `lcid`  
 [in]类型库的本地化 ID。  
  
 `wMajorVersion`  
 [in]主版本号，类型库。 例如，对于版本*x.y*，主版本号是*x*。  
  
 `wMinorVersion`  
 [in]类型库次版本号。 例如，对于版本*x.y*，次版本号是*y*。  
  
 `syskind`  
 [in]A [SYSKIND](http://msdn.microsoft.com/library/662048b2-59a8-48ca-9e4f-2f9a5306faa1)标识操作环境的标志。 常见的值为 SYS_WIN32 和 SYS_WIN64。  
  
 `pbstrResolvedTlbName`  
 [out]指向的指针[BSTR](http://msdn.microsoft.com/library/1b2d7d2c-47af-4389-a6b6-b01b7e915228) ，其中包含在名为的类型库的完整路径`bstrSimpleName`参数。  
  
## <a name="remarks"></a>备注  
 `ResolveTypeLib`方法由调用[LoadTypeLibWithResolver 函数](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)期间[Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)处理。  
  
 此接口的自定义实现必须返回[BSTR](http://msdn.microsoft.com/library/1b2d7d2c-47af-4389-a6b6-b01b7e915228) ，其中包含在名为的类型库的完整路径`bstrSimpleName`参数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** TlbRef.idl、 TlbRef.h  
  
 **库：** TlbRef.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Tlbexp Helper 函数](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx](http://msdn.microsoft.com/library/56a7f9e1-810b-4a42-aa4d-691f4304f5ef)
