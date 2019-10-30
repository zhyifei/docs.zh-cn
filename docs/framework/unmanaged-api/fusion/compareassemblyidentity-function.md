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
ms.openlocfilehash: f6711902fb9d5c5c16084057b731746843cf0230
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108913"
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
 中布尔标志，指示 `pwzAssemblyIdentity1`的用户指定的统一。  
  
 `pwzAssemblyIdentity2`  
 中比较中第二个程序集的文本标识。  
  
 `fUnified2`  
 中布尔标志，指示 `pwzAssemblyIdentity2`的用户指定的统一。  
  
 `pfEquivalent`  
 弄指示两个程序集是否等效的布尔型标志。  
  
 `pResult`  
 弄[AssemblyComparisonResult](assemblycomparisonresult-enumeration.md)枚举，其中包含有关比较的详细信息。  
  
## <a name="return-value"></a>返回值  
 `pfEquivalent` 返回一个布尔值，该值指示两个程序集是否等效。 `pResult` 返回 `AssemblyComparisonResult` 值之一，以便为 `pfEquivalent`的值提供更详细的原因。  
  
## <a name="remarks"></a>备注  
 `CompareAssemblyIdentity` 检查 `pwzAssemblyIdentity1` 和 `pwzAssemblyIdentity2` 是否等效。 在以下一个或多个条件下，`pfEquivalent` 设置为 `true`：  
  
- 这两个程序集标识是等效的。 对于强名称程序集，等效要求程序集名称、版本、公钥标记和区域性完全相同。 对于简单命名的程序集，等效要求程序集名称和区域性匹配。  
  
- 这两个程序集标识都是指在 .NET Framework 上运行的程序集。 即使程序集版本号不匹配，此条件也将返回 `true`。  
  
- 这两个程序集不是托管程序集，但 `fUnified1` 或 `fUnified2` 设置为 `true`。  
  
 `fUnified` 标志指示在强名称程序集的版本号之前的所有版本号都被视为等效于强名称程序集。 例如，如果 `pwzAssemblyIndentity1` 的值为 "MyAssembly，version = 3.0.0.0，culture = 中立，publicKeyToken = ..."，并且 `fUnified1` 的值为 `true`，则表示从版本0.0.0.0 到3.0.0.0 的 MyAssembly 的所有版本均应视为项. 在这种情况下，如果 `pwzAssemblyIndentity2` 引用与 `pwzAssemblyIndentity1`相同的程序集，除非它具有较低的版本号，`pfEquivalent` 设置为 `true`。 如果 `pwzAssemblyIdentity2` 引用较高的版本号，则仅当 `fUnified2` 的值为 `true`时，才将 `pfEquivalent` 设置为 `true`。  
  
 `pResult` 参数包含有关两个程序集被视为等效或不等效的原因的具体信息。 有关详细信息，请参阅[AssemblyComparisonResult 枚举](assemblycomparisonresult-enumeration.md)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成全局静态函数](fusion-global-static-functions.md)
- [AssemblyComparisonResult 枚举](assemblycomparisonresult-enumeration.md)
