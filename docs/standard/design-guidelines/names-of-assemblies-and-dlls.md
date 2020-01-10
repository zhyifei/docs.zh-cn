---
title: 程序集和 DLL 的名称
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: eebccba0b923b04333f289a85330d190c31013ab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709252"
---
# <a name="names-of-assemblies-and-dlls"></a>程序集和 DLL 的名称
程序集是托管代码程序的部署和标识单元。 虽然程序集可以跨一个或多个文件，但通常程序集与 DLL 是一对一映射的。 因此，本部分仅描述 DLL 命名约定，然后可以将其映射到程序集命名约定。  
  
 **✓ 要** 为程序集 DLL 选择能够使人联想到大量功能的名称，例如 System.Data。  
  
 程序集和 DLL 名称不必与命名空间名称相对应，但在命名程序集时应采用命名空间名称。 通常是根据程序集中包含的命名空间的公共前缀来命名 DLL。 例如，如果程序集的两个命名空间为 `MyCompany.MyTechnology.FirstFeature` 和 `MyCompany.MyTechnology.SecondFeature`，则可将其命名为 `MyCompany.MyTechnology.dll`。  
  
 **✓ 考虑**按照下面的模式命名 Dll：  
  
 `<Company>.<Component>.dll`  
  
 其中 `<Component>` 包含一个或多个以句点分隔的子句。 例如：  
  
 `Litware.Controls.dll`。  
  
 *部分©2005，2009 Microsoft Corporation。保留所有权利。*  
  
 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。  
  
## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
