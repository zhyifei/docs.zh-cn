---
title: 面向多个平台的库的应用程序资源
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multiple platforms, resources for
- resources [.NET Framework]
- .NET Framework, resources when targeting multiple platforms
- resources, for multiple platforms
- targeting multiple platforms, resources for
ms.assetid: 72c76f0b-7255-4576-9261-3587f949669c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b32c2e354ea48e25ddb0aa561eb576cbfd89e3fb
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204743"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>面向多个平台的库的应用程序资源
You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) project type to ensure that resources in your class libraries can be accessed from multiple platforms. This project type is available in Visual Studio 2012 and targets the portable subset of the .NET Framework class library. Using  a Portable Class Library ensures that your library can be accessed from desktop apps, Silverlight apps, Windows Phone apps, and Windows 8.x Store apps.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 The Portable Class Library project makes only a very limited subset of the types in the <xref:System.Resources> namespace available to your application, but it does allow you to use the <xref:System.Resources.ResourceManager> class to retrieve resources. 但是，如果你使用 Visual Studio 创建应用，则应使用 Visual Studio 创建的强类型包装器而不是直接使用 <xref:System.Resources.ResourceManager> 类。

 To create a strongly typed wrapper in Visual Studio, set the main resource file's **Access Modifier** in the Visual Studio Resource Designer to **Public**. 这将创建一个包含强类型 ResourceManager 包装器的 [resourceFileName].designer.cs 或 [resourceFileName].designer.vb 文件。 For more information about using a strongly typed resource wrapper, see the "Generating a Strongly Typed Resource Class" section in the [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) topic.

## <a name="resource-manager-in-the-portable-class-library"></a>Resource Manager in the Portable Class Library
 In a Portable Class Library project, all access to resources is handled by the <xref:System.Resources.ResourceManager> class. Because types in the <xref:System.Resources> namespace, such as <xref:System.Resources.ResourceReader> and <xref:System.Resources.ResourceSet>, are not accessible from a Portable Class Library project, they cannot be used to access resources.

 The Portable Class Library project includes the four <xref:System.Resources.ResourceManager> members listed in the following table. 这些构造函数和方法使你能够实例化 <xref:System.Resources.ResourceManager> 对象和检索字符串资源。

|`ResourceManager` 成员|描述|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|创建一个可访问在指定程序集中找到的已命名资源文件的 <xref:System.Resources.ResourceManager> 实例。|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|创建一个与指定类型对应的 <xref:System.Resources.ResourceManager> 实例。|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|检索当前区域性的已命名资源。|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|检索属于指定区域性的已命名资源。|

 The exclusion of other <xref:System.Resources.ResourceManager> members from the Portable Class Library means that serialized objects, non-string data, and images cannot be retrieved from a resource file. To use resources from a Portable Class Library, you should store all  object data in string form. 例如，你可以通过将数值转换为字符串来将其存储在资源文件中，并且你可以检索它们，然后使用数字数据类型的 `Parse` 或 `TryParse` 方法将其转换回数字。 你可通过调用 <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> 方法将图像或其他二进制数据转换为字符串表示形式，并通过调用 <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType> 方法将其还原到字节数组。

## <a name="the-portable-class-library-and-windows-store-apps"></a>The Portable Class Library and Windows Store Apps
 Portable Class Library projects store resources in .resx files, which are then compiled into .resources files and embedded in the main assembly or in satellite assemblies at compile time. Windows 8.x Store apps, on the other hand, require resources to be stored in .resw files, which are then compiled into a single package resource index (PRI) file. However, despite the incompatible file formats, your Portable Class Library will work in a Windows 8.x Store app.

 To consume your class library from a Windows 8.x Store app, add a reference to it in your Windows Store app project. Visual Studio will transparently extract the resources from your assembly into a .resw file and use it to generate a PRI file from which the Windows Runtime can extract resources. At run time, the Windows Runtime executes the code in your Portable Class Library, but it retrieves your Portable Class Library's resources from the PRI file.

 If your Portable Class Library project includes localized resources, you use the hub-and-spoke model to deploy them just as you would for a library in a desktop app. To consume your main resource file and any localized resource files in your Windows 8.x Store app, you add a reference to the main assembly. 在编译时，Visual Studio 会将你的主资源文件以及所有本地化资源文件中的资源提取到单独的 .resw 文件中。 It then compiles the .resw files into a single PRI file that the Windows Runtime accesses at run time.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Example: Non-Localized Portable Class Library
 The following simple, non-localized Portable Class Library example uses resources to store the names of columns and to determine the number of characters to reserve for tabular data. 此示例使用名为 LibResources.resx 的文件存储下表中列出的字符串资源。

|资源名称|资源值|
|-------------------|--------------------|
|Born|Birthdate|
|BornLength|12|
|Hired|雇佣日期|
|HiredLength|12|
|Id|Id|
|ID.Length|12|
|“属性”|“属性”|
|NameLength|25|
|Title|Employee Database|

 The following code defines a `UILibrary` class that uses the Resource Manager wrapper named `resources` generated by Visual Studio when the **Access Modifier** for the file is changed to **Public**. UILibrary 类根据需要分析字符串数据。 方法。 请注意，该类位于 `MyCompany.Employees` 命名空间中。

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 以下代码阐释如何从控制台模式应用访问 `UILibrary` 类及其资源。 It requires a reference to UILibrary.dll to be added to the console app project.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 The following code illustrates how the `UILibrary` class and its resources can be accessed from a Windows 8.x Store app. It requires a reference to UILibrary.dll to be added to the Windows Store app project.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Example: Localized Portable Class Library
 The following localized Portable Class Library example includes resources for the French (France) and English (United States) cultures. The English (United States) culture is the app's default culture; its resources are shown in the table in the [previous section](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). 法语（法国）区域性的资源文件命名为 LibResources.fr-FR.resx，该文件包含下表中列出的字符串资源。 `UILibrary` 类的源代码与上一部分中所示的相同。

|资源名称|资源值|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Date embauché|
|HiredLength|16|
|Id|Id|
|“属性”|Nom|
|Title|Base de données des employés|

 以下代码阐释如何从控制台模式应用访问 `UILibrary` 类及其资源。 It requires a reference to UILibrary.dll to be added to the console app project.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 The following code illustrates how the `UILibrary` class and its resources can be accessed from a Windows 8.x Store app. It requires a reference to UILibrary.dll to be added to the Windows Store app project. 它使用静态 `ApplicationLanguages.PrimaryLanguageOverride` 属性将应用的首选语言设置为法语。

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Resources.ResourceManager>
- [桌面应用中的资源](../../../docs/framework/resources/index.md)
- [打包和部署资源](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
