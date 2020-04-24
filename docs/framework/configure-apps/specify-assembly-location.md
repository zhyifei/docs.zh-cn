---
title: 指定程序集的位置
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646033"
---
# <a name="specifying-an-assemblys-location"></a>指定程序集的位置
有两种方法可以指定程序集的位置：  
  
- 使用[\<代码库>](./file-schema/runtime/codebase-element.md)元素。  
  
- 使用[\<探测>](./file-schema/runtime/probing-element.md)元素。  
  
 您还可以使用[.NET 框架配置工具 （Mscorcfg.msc）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100))指定程序集位置或指定要探测程序集的通用语言运行时的位置。  
  
## <a name="using-the-codebase-element"></a>使用\<代码库>元素  
 只能在计算机配置或发布者策略文件中使用**\<codeBase>** 元素，这些文件也会重定向程序集版本。 当运行时确定要使用的程序集版本时，它将从确定版本的文件中应用代码库设置。 如果未指示代码库，则以正常方式探测程序集的运行时探测。 有关详细信息，请参阅[运行时如何查找程序集](../deployment/how-the-runtime-locates-assemblies.md)。  
  
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
  
 所有强命名程序集都需要**版本**属性，但对于未强命名的程序集，应省略版本属性。 **\<代码库>** 元素需要**href**属性。 不能在**\<代码库>** 元素中指定版本范围。  
  
> [!NOTE]
> 如果要为未强命名的程序集提供代码基提示，则提示必须指向应用程序基或应用程序基目录的子目录。  
  
## <a name="using-the-probing-element"></a>使用\<探测>元素  
 运行时通过探测查找没有代码库的程序集。 有关探测的详细信息，请参阅[运行时如何查找程序集](../deployment/how-the-runtime-locates-assemblies.md)。  
  
 可以使用应用程序配置文件中的[\<探测>](./file-schema/runtime/probing-element.md)元素来指定运行时在定位程序集时应搜索的子目录。 下面的示例演示如何指定运行时应搜索的目录。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **专用 Path**属性包含运行时应搜索程序集的目录。 如果应用程序位于 C：_程序文件\MyApp，运行时将查找未在 C：*程序文件_MyApp_Bin、C：程序文件\MyApp_Subbin 和 C：程序文件\MyApp_Bin3中指定代码库的程序集。 **在私有路径**中指定的目录必须是应用程序基础目录的子目录。  
  
## <a name="see-also"></a>另请参阅

- [.NET 中的程序集](../../standard/assembly/index.md)
- [使用程序集编程](../../standard/assembly/index.md)
- [运行时如何定位程序集](../deployment/how-the-runtime-locates-assemblies.md)
- [使用配置文件配置应用](index.md)
