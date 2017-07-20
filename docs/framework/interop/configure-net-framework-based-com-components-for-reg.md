---
title: "如何：配置基于 .NET Framework 的 COM 组件以进行免注册激活 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "激活, 免注册"
  - "应用程序清单 [.NET Framework]"
  - "组件 [.NET Framework], 清单"
  - "清单 [.NET Framework]"
  - "免注册 COM 互操作, 配置基于 .NET 的组件"
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 如何：配置基于 .NET Framework 的 COM 组件以进行免注册激活
免注册激活对于基于 .NET Framework 的组件仅比对于 COM 组件稍微复杂一些。  安装程序需要两个清单：  
  
-   COM 应用程序必须有一个 Win32 样式的应用程序清单，用于标识托管组件。  
  
-   基于 .NET Framework 的组件必须有一个包含运行时所需激活信息的组件清单。  
  
 本主题讲解如何将应用程序清单与应用程序关联起来；如何将组件清单与组件关联起来；以及如何在程序集中嵌入组件清单。  
  
### 创建应用程序清单  
  
1.  对于与一个或多个托管组件交互操作的 COM 应用程序，使用 XML 编辑器创建（或修改）该应用程序拥有的应用程序清单。  
  
2.  在文件开头插入以下标准头：  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     如想查看清单元素及其特性的信息，请在 MSDN Library 中搜索“应用程序清单参考”。  
  
3.  确定该清单的所有者。  在下面的示例中，`myComApp` 版本 1 拥有该清单文件。  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  确定相关程序集。  在下面的示例中，`myComApp` 依赖于 `myManagedComp`。  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  保存并命名清单文件。  应用程序清单的名称是在程序集可执行文件名的后面加上 .manifest 扩展名。  例如，myComApp.exe 的应用程序清单文件的名称为 myComApp.exe.manifest。  
  
 可将应用程序清单与 COM 应用程序安装在相同的目录中。  或者，也可将其作为资源添加到应用程序的 .exe 文件中。  如想查看其他信息，请在 MSDN Library 中搜索“并行程序集”。  
  
#### 创建组件清单  
  
1.  使用 XML 编辑器创建一个组件清单来描述托管程序集。  
  
2.  在文件开头插入以下标准头：  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  确定该文件的所有者。  应用程序清单文件中 `<dependentAssembly>` 元素的 `<assemblyIdentity>` 元素必须与组件清单中的相应元素匹配。  在下面的示例中，`myManagedComp` 版本 1.2.3.4 拥有该清单文件。  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  确定程序集中的各个类。  使用 `<clrClass>` 元素可以唯一地标识托管程序集中的各个类。  该元素是 `<assembly>` 元素的子元素，它具有下表所示的特性。  
  
    |特性|描述|必需|  
    |--------|--------|--------|  
    |`clsid`|指定要激活的类的标识符。|是|  
    |`description`|用于向用户提供组件信息的字符串。  默认为空字符串。|否|  
    |`name`|表示该托管类的字符串。|是|  
    |`progid`|用于后期绑定激活的标识符。|否|  
    |`threadingModel`|COM 线程模型。默认值为"Both”。|否|  
    |`runtimeVersion`|指定要使用的公共语言运行时 \(CLR\) 版本。  如果未指定此特性，并且尚未加载 CLR，则将使用 CLR 版本 4 之前的已安装的最新版本来加载组件。  如果指定 v1.0.3705、v1.1.4322 或 v2.0.50727，则此版本自动向前滚动到 CLR 版本 4 之前的已安装的最新 CLR 版本（通常为 v2.0.50727）。  如果已经加载 CLR 的其他版本，并且指定的版本可以在进程内并行加载，则加载指定的版本；否则，将使用已加载的 CLR。  这可能会导致加载失败。|否|  
    |`tlbid`|包含有关该类的类型信息的类型库的标识符。|否|  
  
     所有特性标记均区分大小写。  可以通过使用 OLE\/COM ObjectViewer \(Oleview.exe\) 查看导出的类型库来获取 CLSID、ProgID、线程模型，以及运行时版本。  
  
     下面的组件清单标识两个类：`testClass1` 和 `testClass2`。  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4" />  
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  保存并命名清单文件。  组件清单的名称是在程序库名称的后面加上 .manifest 扩展名。  例如，myManagedComp.dll 的组件清单的名称为 myManagedComp.manifest。  
  
 必须将组件清单作为资源嵌入程序集。  
  
#### 在托管程序集中嵌入组件清单  
  
1.  创建包含以下语句的资源脚本：  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     在这条语句中，`myManagedComp.manifest` 是要嵌入的组件清单的名称。  此示例中，脚本文件名是 `myresource.rc`。  
  
2.  用 Microsoft Windows 资源编译器 \(Rc.exe\) 编译脚本。  在命令提示符处，键入下列命令：  
  
     `rc myresource.rc`  
  
     Rc.exe 产生 `myresource.res` 资源文件。  
  
3.  再次编译该程序集的源文件，并使用 **\/win32res** 选项指定资源文件：  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     同样，`myresource.res` 是包含嵌入的资源的资源文件的名称。  
  
## 请参阅  
 [免注册 COM 互操作](../../../docs/framework/interop/registration-free-com-interop.md)   
 [Requirements for Registration\-Free COM Interop](http://msdn.microsoft.com/zh-cn/0c43bc57-eecf-4e6c-8114-490141cce4da)   
 [Configuring COM Components for Registration\-Free Activation](http://msdn.microsoft.com/zh-cn/bfe9b02f-d964-4784-960e-a1f94692fbfe)   
 [基于 .NET 组件的免注册激活：一个演示链接](http://go.microsoft.com/fwlink/?LinkId=158812)