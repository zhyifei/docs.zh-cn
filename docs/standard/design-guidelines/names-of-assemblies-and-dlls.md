---
title: 程序集和 DLL 的名称
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6cf175472d68e99598dd56e170bee3d37ae3c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="names-of-assemblies-and-dlls"></a>程序集和 DLL 的名称
程序集是部署和托管的代码程序的标识的单元。 程序集可以跨一个或多个文件，尽管通常程序集进行一对一映射 DLL。 因此，本部分介绍了唯一 DLL 命名约定，然后可以映射到程序集命名约定。  
  
 **✓ 执行**选择您的程序集建议的功能，例如 System.Data 大量的 Dll 的名称。  
  
 程序集和 DLL 名称无需对应于命名空间名称，但它是合理命名程序集时应遵循的命名空间名称。 好的经验法则是名称的公共前缀的程序集中包含的命名空间所基于的 DLL。 例如，包含两个命名空间中的程序集`MyCompany.MyTechnology.FirstFeature`和`MyCompany.MyTechnology.SecondFeature`，无法调用`MyCompany.MyTechnology.dll`。  
  
 **请考虑 ✓**按照下面的模式命名 Dll:  
  
 `<Company>.<Component>.dll`  
  
 其中`<Component>`包含一个或多个以点分隔的子句。 例如：  
  
 `Litware.Controls.dll`。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
