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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796316"
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
 `pwzAssemblyReference`参数是指向字符串的指针，该字符串包含程序集的名称。  
  
 如果此程序集是 .NET Framework 的一部分，则`pbIsFrameworkAssembly`参数将包含的`true`布尔值。  
  
 如果命名的程序集不是 .NET Framework 的一部分，或者如果`pwzAssemblyReference`参数不命名程序集， `pbIsFrameworkAssembly`则将包含的`false`布尔值。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
## <a name="see-also"></a>请参阅

- [合成全局静态函数](fusion-global-static-functions.md)
