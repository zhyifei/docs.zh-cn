---
title: 重大更改和.NET 库
description: 有关在中导航时创建的.NET 库的重大更改的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "49369808"
---
# <a name="breaking-changes"></a>重大更改

非常重要的.NET 库，以查找现有用户的稳定性和未来的创新之间的平衡。 库作者依赖于重构和重新考虑代码，直到完美，但是破坏现有用户会造成负面影响，尤其是对于低级别库。

## <a name="project-types-and-breaking-changes"></a>项目类型和重大更改

.NET 社区如何使用库更改对最终用户开发人员的重大更改的效果。

* **低和中间级库**如序列化程序、 HTML 分析器、 数据库对象关系映射器中或 web 框架的最受影响的重大更改。

  构建基块包是通过最终用户开发人员生成应用程序，以及其他库用作 NuGet 依赖项。 例如，您正在构建应用程序，并且使用的开源客户端来调用 web 服务。 客户端使用的依赖项的一个重大更新不是可以解决问题。 它是需要更改的开源客户端，并且你有无法控制。 您必须找到兼容版本的库或提交的客户端库的修复程序并等待新版本。 最坏的情形是如果你想要使用两个依赖于第三个库的互相不兼容版本的库。

* **高级库**等一系列 UI 控件对不太敏感的重大更改。

  最终用户应用程序中直接引用高级库。 如果发生重大更改，开发人员可以选择更新到最新版本，或者可以修改其应用程序以使用重大更改。

**✔️ 执行**考虑将如何使用你的库。 重大更改会在应用程序和使用它的库有何影响？

**✔️ 执行**时开发的低级别.NET 库的重大更改降至最低。

**请考虑 ✔️**发布一个较大的库作为新的 NuGet 包重写。

## <a name="types-of-breaking-changes"></a>类型的重大更改

重大更改划分为不同类别，并不是同样有影响。

### <a name="source-breaking-change"></a>源项重大更改

重大更改的源不会影响程序执行，但会导致编译错误下一次重新编译应用程序。 例如，新重载会产生多义性以前，是明确的方法调用中或已重命名的参数将中断调用方使用的命名参数。

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

仅在开发人员重新编译其应用程序时有害的重大更改的源，因为它是破坏性最小的重大更改。 开发人员可以轻松地解决其自己断开的源的代码。

### <a name="behavior-breaking-change"></a>行为重大更改

行为更改是最常见的重大更改类型： 行为中的几乎所有更改都可能会都破坏人。 更改为你的库，如方法签名异常引发或输入或输出数据格式，所有产生负面影响的库使用者。 如果用户依赖于以前中断的行为，bug 修复，甚至可以限定作为一项重大更改。

添加功能和改进不良行为是件好事，但不小心的情况下它可以使它很难升级的现有用户。 于帮助开发人员处理行为的重大更改的一种方法是隐藏在设置。 设置可让开发人员更新到最新版本的同时选择中选择加入或选择退出的重大更改在你的库。 使用此策略，同时允许其使用的代码，随着时间的推移适应保持最新的开发人员。

例如，ASP.NET Core MVC 提供的概念[兼容性版本](/aspnet/core/mvc/compatibility-version)修改功能启用和禁用上`MvcOptions`。

**请考虑 ✔️**离开的新功能默认情况下，如果它们会影响现有用户，让开发人员选择启用该功能的设置。

### <a name="binary-breaking-change"></a>二进制的重大更改

更改你的库的公共 API 时发生的重大更改的二进制文件，以便根据编译的程序集的库的较旧版本将不再能够调用 API。 例如，通过添加一个新的参数来更改方法的签名将导致针对较旧版本的库编译的程序集引发<xref:System.MissingMethodException>。

重大更改的二进制文件也会中断**整个程序集**。 重命名的程序集包含`AssemblyName`也会添加、 删除或更改程序集的强命名密钥会更改程序集的标识。 程序集的标识的更改将中断所有使用它的已编译的代码。

**不这样做 ❌**更改程序集名称。

**不这样做 ❌**添加、 删除或更改的强命名密钥。

**请考虑 ✔️**使用而不接口的抽象基类。

> 向接口添加任何内容将导致它无法实现的现有类型。 一个抽象基类，可添加默认虚拟实现。

**请考虑 ✔️**放置<xref:System.ObsoleteAttribute>类型和想要删除的成员。 该属性应更新代码以不能再使用已过时 API 的说明。

> 调用具有类型和方法的代码<xref:System.ObsoleteAttribute>将生成一个生成警告消息提供给该属性。 警告让人客户使用已过时的 API 图面上时为迁移，以便在删除过时的 API，大多数都不能再使用它。

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

## <a name="see-also"></a>请参阅

* [C# 开发人员的版本和更新注意事项](../../csharp/whats-new/version-update-considerations.md)
* [在.NET 中的 API 重大更改到权威指南](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [CoreFX 重大更改规则](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[上一篇](./versioning.md)
