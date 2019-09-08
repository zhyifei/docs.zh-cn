---
title: 合成接口
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1605605f8510f7ccf5f0bbf2f3f6b09050a16025
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795302"
---
# <a name="fusion-interfaces"></a>合成接口
本节介绍了合成 API 用于访问应用程序资源属性的非托管接口，并为应用程序定位了这些资源的正确版本。  
  
## <a name="in-this-section"></a>本节内容  
 [IAppIdAuthority 接口](iappidauthority-interface.md)  
 提供一些方法，这些方法可为应用程序标识和引用生成和比较键。  
  
 [IAssemblyCache 接口](iassemblycache-interface.md)  
 提供全局程序集缓存的表示形式。  
  
 [IAssemblyCacheItem 接口](iassemblycacheitem-interface.md)  
 表示全局程序集缓存中的单个程序集。  
  
 [IAssemblyEnum 接口](iassemblyenum-interface.md)  
 表示`IAssemblyName`对象数组的枚举器。  
  
 [IAssemblyName 接口](iassemblyname-interface.md)  
 提供用于描述和处理程序集的唯一标识的方法。  
  
 [IDefinitionAppId 接口](idefinitionappid-interface.md)  
 表示定义当前作用域中的应用程序的代码的唯一标识符。  
  
 [IDefinitionIdentity 接口](idefinitionidentity-interface.md)  
 表示定义当前作用域中的应用程序的代码的唯一签名。  
  
 [IEnumDefinitionIdentity 接口](ienumdefinitionidentity-interface.md)  
 用作`IDefinitionIdentity`对象集合的枚举器。  
  
 [IEnumIDENTITY_ATTRIBUTE 接口](ienumidentity-attribute-interface.md)  
 用作当前范围中代码对象的特性的枚举数。  
  
 [IEnumReferenceIdentity 接口](ienumreferenceidentity-interface.md)  
 用作对象集合的`IReferenceIdentity`枚举器。  
  
 [IIdentityAuthority 接口](iidentityauthority-interface.md)  
 管理代码对象的标识键。  
  
 [IInstallReferenceEnum 接口](iinstallreferenceenum-interface.md)  
 表示安装在全局程序集缓存中的被引用程序集的枚举器。  
  
 [IInstallReferenceItem 接口](iinstallreferenceitem-interface.md)  
 表示安装在全局程序集缓存中的项。  
  
 [IReferenceAppId 接口](ireferenceappid-interface.md)  
 表示对当前范围内的应用程序的唯一标识符的引用。  
  
 [IReferenceIdentity 接口](ireferenceidentity-interface.md)  
 表示对代码对象的唯一签名的引用。  
  
## <a name="reference"></a>参考  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a>相关章节  
 [合成全局静态函数](fusion-global-static-functions.md)  
  
 [合成枚举](fusion-enumerations.md)  
  
 [合成结构](fusion-structures.md)
