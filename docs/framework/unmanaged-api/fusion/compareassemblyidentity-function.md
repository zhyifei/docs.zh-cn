---
title: CompareAssemblyIdentity 函数
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b52d3af38bd09ce5864c25d27e148dbd7f4639b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795442"
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity 函数
比较两个程序集标识以确定它们是否等效。  
  
## <a name="syntax"></a>语法  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a>参数  
 `pwzAssemblyIdentity1`  
 中比较中第一个程序集的文本标识。  
  
 `fUnified1`  
 中指示的用户指定的统一的`pwzAssemblyIdentity1`布尔标志。  
  
 `pwzAssemblyIdentity2`  
 中比较中第二个程序集的文本标识。  
  
 `fUnified2`  
 中指示的用户指定的统一的`pwzAssemblyIdentity2`布尔标志。  
  
 `pfEquivalent`  
 弄指示两个程序集是否等效的布尔型标志。  
  
 `pResult`  
 弄[AssemblyComparisonResult](assemblycomparisonresult-enumeration.md)枚举，其中包含有关比较的详细信息。  
  
## <a name="return-value"></a>返回值  
 `pfEquivalent`返回一个布尔值，该值指示两个程序集是否等效。 `pResult`返回`AssemblyComparisonResult`值之一，以便为的`pfEquivalent`值提供更详细的原因。  
  
## <a name="remarks"></a>备注  
 `CompareAssemblyIdentity`、`pwzAssemblyIdentity1`检查和`pwzAssemblyIdentity2`是否等效。 `pfEquivalent`在以下一个`true`或多个条件下，设置为：  
  
- 这两个程序集标识是等效的。 对于强名称程序集，等效要求程序集名称、版本、公钥标记和区域性完全相同。 对于简单命名的程序集，等效要求程序集名称和区域性匹配。  
  
- 这两个程序集标识都是指在 .NET Framework 上运行的程序集。 即使程序集`true`版本号不匹配，此条件也将返回。  
  
- 这两个程序集不是托管程序`fUnified1`集`fUnified2` ，而是`true`设置为。  
  
 该`fUnified`标志指示在强名称程序集的版本号之前的所有版本号都被视为等效于强名称程序集。 例如，如果的值`pwzAssemblyIndentity1`为 "MyAssembly，version = 3.0.0.0，culture = 中立，publicKeyToken = ..."，并且的`fUnified1`值为，则`true`表示从版本0.0.0.0 到3.0.0.0 的 MyAssembly 的所有版本都应该为视为等效。 在这种情况下， `pwzAssemblyIndentity2`如果引用与相同的`pwzAssemblyIndentity1`程序集，则将设置为`true`，但该程序`pfEquivalent`集的版本号较低。 如果`pwzAssemblyIdentity2`引用较高的版本号，则`pfEquivalent`仅当的`true` `fUnified2`值为时`true`，才设置为。  
  
 参数`pResult`包含有关两个程序集被视为等效或不等效的原因的具体信息。 有关详细信息，请参阅[AssemblyComparisonResult 枚举](assemblycomparisonresult-enumeration.md)。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成全局静态函数](fusion-global-static-functions.md)
- [AssemblyComparisonResult 枚举](assemblycomparisonresult-enumeration.md)
