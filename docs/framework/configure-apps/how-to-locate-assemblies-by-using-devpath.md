---
title: 如何：使用 DEVPATH 查找程序集
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 9b8e3c89c13e7f5c294afca54af7f63293653e87
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408783"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>如何：使用 DEVPATH 查找程序集
开发人员可能想要确保它们生成的共享程序集与多个应用程序一起正常运行。 而不是不断地将在全局程序集缓存中的程序集放在开发周期中，开发人员可以创建指向程序集的生成输出目录 DEVPATH 环境变量。  
  
 例如，假设您要构建调用 MySharedAssembly 共享程序集和输出目录是 C:\MySharedAssembly\Debug。 可以将 C:\MySharedAssembly\Debug 放 devpath 查找程序集变量中。 然后，必须指定[ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)计算机配置文件中的元素。 此元素指示公共语言运行时使用 devpath 查找程序集来定位程序集。  
  
 共享程序集必须可由运行时检测到。  若要指定用于解析程序集引用使用的专用目录[ \<b a s e > 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)或[\<探测 > 元素](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)在配置文件中，如中所述[指定程序集位置](../../../docs/framework/configure-apps/specify-assembly-location.md)。  此外可以将程序集放置在应用程序目录的子目录中。 有关更多信息，请参阅 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。  
  
> [!NOTE]
>  这是一项高级的功能，仅供开发。  
  
 下面的示例演示如何会导致运行时用于搜索由 DEVPATH 环境变量指定的目录中的程序集。  
  
## <a name="example"></a>示例  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 此设置默认值为 false。  
  
> [!NOTE]
>  仅在开发期间使用此设置。 在运行时不会检查位于 devpath 查找程序集强名称的程序集上的版本。 它只需使用它找到的第一个程序集。  
  
## <a name="see-also"></a>请参阅  
 [配置.NET Framework 应用](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
