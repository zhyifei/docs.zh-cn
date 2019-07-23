---
title: C# 语言版本控制 - C# 指南
description: 了解如何根据项目确定 C# 语言版本，以及可以手动调整的不同值。
ms.date: 07/10/2019
ms.openlocfilehash: e35fdf2bcdb1a31b752c760f3f6df59232e498a4
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236100"
---
# <a name="c-language-versioning"></a>C# 语言版本控制

C# 编译器根据项目的一个或多个目标框架确定默认语言版本。 这是因为 C# 语言可能具有依赖于每个 .NET 实现中不提供的类型或运行时组件的功能。 这也确保了无论根据哪种目标构建项目，默认情况下你都将获得最兼容的语言版本。

## <a name="defaults"></a>默认值

编译器根据以下规则确定默认值：

|目标框架|version|C# 语言版本的默认值|
|----------------|-------|---------------------------|
|.NET Core|3.x|C# 8.0|
|.NET Core|2.x|C# 7.3|
|.NET Standard|全部|C# 7.3|
|.NET Framework|全部|C# 7.3|

## <a name="default-for-previews"></a>默认值适用于预览版

如果你的项目是以具有相应预览语言版本的预览框架为目标，那么使用的语言版本是预览语言版本。 这可确保你可以使用保证在任何环境中都可用的预览提供的最新功能，而不会影响面向发布的 .NET Core 版本的项目。

## <a name="overriding-a-default"></a>重写默认值

如果必须明确指定 C# 版本，可以通过以下几种方式实现：

- 手动编辑[项目文件](#edit-the-project-file)。
- 为[子目录中的多个项目](#configure-multiple-projects)设置语言版本。
- 配置 [`-langversion` 编译器选项](compiler-options/langversion-compiler-option.md)

### <a name="edit-the-project-file"></a>编辑项目文件

可在项目文件中设置语言版本。 例如，如果你明确希望访问预览功能，则可以添加如下元素：

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

值 `preview` 使用编译器支持的最新可用的 C# 语言预览版。

### <a name="configure-multiple-projects"></a>配置多个项目

可以创建包含 `<LangVersion>` 元素的 Directory.Build.props  文件来配置多个目录。 通常是在解决方案目录中完成这件事。 将以下内容添加到解决方案目录中的 Directory.Build.props  文件：

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

现在，包含该文件的目录的每个子目录中的版本都将使用 C# 预览版。 有关详细信息，请参阅关于[自定义生成](/visualstudio/msbuild/customize-your-build)的文章。

## <a name="c-language-version-reference"></a>C# 语言版本引用

下表显示当前所有 C# 语言版本。 如果编译器较旧，它可能不一定了解每个值。 如果安装的是 .NET Core 3.0，则你可以访问列出的所有内容。

|值|含义|
|------------|-------------|
|preview|编译器接受最新预览版中的所有有效语言语法。|
|最新|编译器接受最新发布的编译器版本（包括次要版本）中的语法。|
|latestMajor|编译器接受最新发布的编译器主要版本中的语法。|
|8.0|编译器只接受 C# 8.0 或更低版本中所含的语法。|
|7.3|编译器只接受 C# 7.3 或更低版本中所含的语法。|
|7.2|编译器只接受 C# 7.2 或更低版本中所含的语法。|
|7.1|编译器只接受 C# 7.1 或更低版本中所含的语法。|
|7|编译器只接受 C# 7.0 或更低版本中所含的语法。|
|6|编译器只接受 C# 6.0 或更低版本中所含的语法。|
|5|编译器只接受 C# 5.0 或更低版本中所含的语法。|
|4|编译器只接受 C# 4.0 或更低版本中所含的语法。|
|3|编译器只接受 C# 3.0 或更低版本中所含的语法。|
|ISO-2|编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法 |
|ISO-1|编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法 |
