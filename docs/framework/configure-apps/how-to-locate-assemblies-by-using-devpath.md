---
title: "如何：使用 DEVPATH 查找程序集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0944f2798c45a039149baaa6e46ce2b56eb5c5df
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>如何：使用 DEVPATH 查找程序集
开发人员可能想要确保它们在构建共享程序集与多个应用程序一起正常运行。 而不是不断地将全局程序集缓存中的程序集放置在开发周期中，开发人员可以创建一个 DEVPATH 环境变量，指向程序集的生成输出目录。  
  
 例如，假定您构建了调用 MySharedAssembly 共享程序集和输出目录是 C:\MySharedAssembly\Debug。 你可以放置 C:\MySharedAssembly\Debug DEVPATH 变量中。 你必须随后指定[ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)计算机配置文件中的元素。 此元素指示公共语言运行时使用 DEVPATH 查找程序集。  
  
 共享程序集必须由运行时可发现。  若要指定用于解析程序集引用使用专用目录[\<基本代码 > 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)或[\<探测 > 元素](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)在配置文件中中, 所述[指定程序集的位置](../../../docs/framework/configure-apps/specify-assembly-location.md)。  此外可以将程序集放置在应用程序目录的子目录中。 有关更多信息，请参阅 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。  
  
> [!NOTE]
>  这是一项高级的功能，仅用于开发。  
  
 下面的示例演示如何使运行时搜索 DEVPATH 环境变量指定的目录中的程序集。  
  
## <a name="example"></a>示例  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 此设置默认为 false。  
  
> [!NOTE]
>  仅在开发期间使用此设置。 运行时不会检查上 DEVPATH 中找到的具有强名称的程序集的版本。 它只需使用它找到的第一个程序集。  
  
## <a name="see-also"></a>请参阅  
 [配置.NET Framework 应用](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
