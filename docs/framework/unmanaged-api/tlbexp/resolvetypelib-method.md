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
ms.openlocfilehash: 46cd8b5c22f48ba45c4da7fa8876d6807a21f2b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124143"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib 方法
通过返回类型库的完全限定路径来解析该类型库的简单名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a>参数  
 `bstrSimpleName`  
 中一个[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) ，其中包含类型库的简单名称。  
  
 `tlbid`  
 中分配给注册表中的类型库的 GUID。  
  
 `lcid`  
 中类型库的本地化 ID。  
  
 `wMajorVersion`  
 中类型库的主版本号。 例如，对于版本*x. y*，主版本号是*x*。  
  
 `wMinorVersion`  
 中类型库的次版本号。 例如，对于版本*x. y*，次版本号为*y*。  
  
 `syskind`  
 中标识操作环境的[SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind)标志。 常见值为 SYS_WIN32 和 SYS_WIN64。  
  
 `pbstrResolvedTlbName`  
 弄指向包含在 `bstrSimpleName` 参数中命名的类型库的完整路径的[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr)的指针。  
  
## <a name="remarks"></a>备注  
 `ResolveTypeLib` 方法由[LoadTypeLibWithResolver 函数](loadtypelibwithresolver-function.md)在[Tlbexp.exe （类型库导出程序）](../../tools/tlbexp-exe-type-library-exporter.md)处理期间调用。  
  
 此接口的自定义实现必须返回包含 `bstrSimpleName` 参数中名为的类型库的完整路径的[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** TlbRef，TlbRef  
  
 **库：** TlbRef  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Tlbexp Helper 函数](index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
