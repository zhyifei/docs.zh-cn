---
title: "指定程序集 &#39; s 位置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 5f79ed7af91f2e54edbc2174da2afa1b3cb56557
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-an-assembly39s-location"></a>指定程序集 &#39; s 位置
有两种方法来指定程序集的位置：  
  
-   使用[\<基本代码 >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)元素。  
  
-   使用[\<探测 >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)元素。  
  
 你还可以使用[.NET Framework 配置工具 (Mscorcfg.msc)](http://msdn.microsoft.com/en-us/a7106c52-68da-490e-b129-971b2c743764)以指定程序集的位置或指定为公共语言运行时来探测程序集的位置。  
  
## <a name="using-the-codebase-element"></a>使用\<基本代码 > 元素  
 你可以使用**\<基本代码 >**仅在计算机配置文件或发布服务器策略文件也重定向程序集版本程序中的元素。 当运行时确定要使用的程序集版本时，它适用确定版本的文件中的基本代码设置。 如果指示没有基本代码，运行时探测程序集以正常方式。 有关详细信息，请参阅[运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。  
  
 下面的示例演示如何指定程序集的位置。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **版本**属性是必需的所有具有强名称程序集，但应省略不具有强名称的程序集。 **\<基本代码 >**元素需要**href**属性。 你不能指定版本范围中的**\<基本代码 >**元素。  
  
> [!NOTE]
>  如果你所提供的不是具有强名称程序集的基本代码的提示，提示必须指向应用程序基或应用程序基目录的子目录。  
  
## <a name="using-the-probing-element"></a>使用\<探测 > 元素  
 运行时定位通过探测没有的基本代码的程序集。 有关探测的详细信息，请参阅[运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。  
  
 你可以使用[\<探测 >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)应用程序配置文件来指定运行时应搜索在查找程序集的子目录中的元素。 下面的示例演示如何指定运行时应搜索的目录。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **PrivatePath**属性包含运行时应搜索程序集的目录。 如果应用程序位于 C:\Program Files\MyApp，运行时将查找没有在 C:\Program Files\MyApp\Bin、 C:\Program Files\MyApp\Bin2\Subbin 和 C:\Program Files\MyApp\Bin3 中指定的基本代码的程序集。 中指定的目录**privatePath**必须是应用程序基目录的子目录。  
  
## <a name="see-also"></a>请参阅  
 [Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）  
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [配置.NET Framework 应用](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
