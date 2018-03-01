---
title: "CompareAssemblyIdentity 函数"
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
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 266868a65a0db75b57d46d92a469b4b6ceaa88e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity 函数
比较两个程序集标识，以确定它们是否等效。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a>参数  
 `pwzAssemblyIdentity1`  
 [in]文本中比较的第一个程序集标识。  
  
 `fUnified1`  
 [in]一个布尔型标志，该值指示用户指定的统一`pwzAssemblyIdentity1`。  
  
 `pwzAssemblyIdentity2`  
 [in]文本中比较的第二个程序集标识。  
  
 `fUnified2`  
 [in]一个布尔型标志，该值指示用户指定的统一`pwzAssemblyIdentity2`。  
  
 `pfEquivalent`  
 [out]一个布尔型标志，该值指示两个程序集是否等效。  
  
 `pResult`  
 [out][AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)枚举，其中包含有关比较的详细的信息。  
  
## <a name="return-value"></a>返回值  
 `pfEquivalent`返回一个布尔值，该值指示两个程序集是否等效。 `pResult`返回的一个`AssemblyComparisonResult`值，以给出的值的详细的原因`pfEquivalent`。  
  
## <a name="remarks"></a>备注  
 `CompareAssemblyIdentity`检查是否`pwzAssemblyIdentity1`和`pwzAssemblyIdentity2`是等效的。 `pfEquivalent`设置为`true`下一个或多个以下条件：  
  
-   两个程序集标识是等效的。 对于强名称程序集，等效性要求的程序集名称、 版本、 公钥标记和区域性视为相同。 对于只需名称的程序集，等效性要求匹配的程序集名称和区域性。  
  
-   这两个程序集标识是指在.NET Framework 运行的程序集。 这种情况返回`true`即使不匹配的程序集版本号。  
  
-   两个程序集不是托管程序集，但`fUnified1`或`fUnified2`已设置为`true`。  
  
 `fUnified`标志指示最大为强名称程序集的版本号的所有版本数字均被都视为等效于强名称程序集。 例如，如果值`pwzAssemblyIndentity1`是"MyAssembly，版本 = 3.0.0.0，区域性 = neutral，publicKeyToken =..."，和的值`fUnified1`是`true`，这表示应从 0.0.0.0 到 3.0.0.0 版本起 MyAssembly 的所有版本视为等效项。 在这种情况下，如果`pwzAssemblyIndentity2`指的是相同的程序集中`pwzAssemblyIndentity1`，只不过它具有较低的版本号，`pfEquivalent`设置为`true`。 如果`pwzAssemblyIdentity2`为更高版本的版本号，是指`pfEquivalent`设置为`true`才的值`fUnified2`是`true`。  
  
 `pResult`参数包括有关为什么两个程序集都被视为等效也不等效的特定信息。 有关详细信息，请参阅[AssemblyComparisonResult 枚举](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [AssemblyComparisonResult 枚举](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
