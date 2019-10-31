---
title: IsFrameworkAssembly 函数
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123073"
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly 函数
获取一个值，该值指示是否托管指定的程序集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>参数  
 `pwzAssemblyReference`  
 中要检查的程序集的名称。  
  
 `pbIsFrameworkAssembly`  
 弄指示程序集是否为托管程序集的布尔值。  
  
 `pwzFrameworkAssemblyIdentity`  
 中一个 uncanonicalized 字符串，其中包含程序集的唯一标识。  
  
 `pccSize`  
 [输入] `pwzFrameworkAssemblyIdentity` 的大小。  
  
## <a name="remarks"></a>备注  
 `pwzAssemblyReference` 参数是指向包含程序集名称的字符串的指针。  
  
 如果此程序集是 .NET Framework 的一部分，则 `pbIsFrameworkAssembly` 参数将包含一个 `true`的布尔值。  
  
 如果命名的程序集不是 .NET Framework 的一部分，或者 `pwzAssemblyReference` 参数未命名程序集，`pbIsFrameworkAssembly` 将包含一个布尔值 `false`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
## <a name="see-also"></a>请参阅

- [合成全局静态函数](fusion-global-static-functions.md)
