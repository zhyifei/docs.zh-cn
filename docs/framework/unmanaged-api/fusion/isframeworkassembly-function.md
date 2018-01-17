---
title: "IsFrameworkAssembly 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IsFrameworkAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IsFrameworkAssembly
helpviewer_keywords: IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa077ce13031772ec2ea20708c1dbd29da02d32a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly 函数
获取一个值，该值指示指定的程序集是否为托管对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a>参数  
 `pwzAssemblyReference`  
 [in]要检查的程序集的名称。  
  
 `pbIsFrameworkAssembly`  
 [out]一个布尔值，该值指示是否已托管程序集。  
  
 `pwzFrameworkAssemblyIdentity`  
 [in]包含程序集的唯一标识一个 uncanonicalized 的字符串。  
  
 `pccSize`  
 [输入] `pwzFrameworkAssemblyIdentity` 的大小。  
  
## <a name="remarks"></a>备注  
 `pwzAssemblyReference`参数是指向包含程序集的名称的字符字符串的指针。  
  
 如果此程序集是.NET Framework 的一部分`pbIsFrameworkAssembly`参数将包含布尔值的`true`。  
  
 如果指定的程序集不属于.NET Framework 中，或如果`pwzAssemblyReference`参数没有命名一个程序集，`pbIsFrameworkAssembly`将包含布尔值的`false`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
## <a name="see-also"></a>请参阅  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
