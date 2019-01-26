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
ms.openlocfilehash: 6558d27f10e5b93dfe2c8053bb96434d49fd3c4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537201"
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
 [in]一个[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) ，其中包含类型库的简单名称。  
  
 `tlbid`  
 [in]分配给在注册表中的类型库的 GUID。  
  
 `lcid`  
 [in]类型库的本地化 ID。  
  
 `wMajorVersion`  
 [in]类型库的主版本号。 例如，对于版本*x.y*，主版本号是*x*。  
  
 `wMinorVersion`  
 [in]类型库的次版本号。 例如，对于版本*x.y*的次版本号是*y*。  
  
 `syskind`  
 [in]一个[SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind)标志，用于标识操作的环境。 常见的值为 SYS_WIN32 和 SYS_WIN64。  
  
 `pbstrResolvedTlbName`  
 [out]一个指向[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) ，其中包含在名为的类型库的完整路径`bstrSimpleName`参数。  
  
## <a name="remarks"></a>备注  
 `ResolveTypeLib`调用方法[LoadTypeLibWithResolver 函数](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)期间[Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)处理。  
  
 自定义此接口的实现必须返回[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) ，其中包含在名为的类型库的完整路径`bstrSimpleName`参数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** TlbRef.idl TlbRef.h  
  
 **库：** TlbRef.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [Tlbexp Helper 函数](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
