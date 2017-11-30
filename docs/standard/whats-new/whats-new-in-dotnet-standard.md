---
title: "什么是.NET 标准中的新增功能"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a>什么是.NET 标准中的新增功能

.NET 标准是定义必须在符合标准的该版本的.NET 实现上可用的 Api 版本控制组形式规范。 .NET Standard 面向库开发者。 在任何支持的标准，该版本的.NET Framework、.NET 核心或 Xamarin 实现中，可以使用面向.NET 标准版本的库。

.NET 标准的最新版本为 2.0。 包含它是与.NET 核心 2.0 SDK，以及 Visual Studio 2017 版本 15.3 与安装.NET 核心工作负荷。

## <a name="supported-net-implementations"></a>受支持的.NET 实现

.NET 标准 2.0 支持以下.NET 实现：

- .NET 核心 2.0
- .NET Framework 4.6.1
- Mono 5.4
- Xamarin.iOS 10.14
- Xamarin.Mac 3.8
- Xamarin.Android 8.0
- 通用 Windows 平台 10.0.16299

## <a name="whats-new-in-the-net-standard-20"></a>什么是.NET 标准 2.0 中的新增功能
 
.NET 标准 2.0 包括以下新功能：

**一组大大扩展的 Api**

通过版本 1.6，.NET 标准包含 Api 的一个相对较小子集。 在的中排除了许多通常在.NET Framework 或 Xamarin 中使用的 Api。 这将增加复杂性开发，因为它要求开发人员查找合适的替代手段，对于熟悉 Api，当它们开发应用程序和面向多个.NET 实现库中时。 .NET 标准 2.0 通过添加超过 20000 详细 Api 不是.NET 标准 1.6，标准的以前版本中可用来解决此限制。 已添加到.NET 标准 2.0 的 Api 的列表，请参阅[.NET 标准 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md)。 

某些上述元素添加到<xref:System>.NET 标准 2.0 中的命名空间包括：

- 支持<xref:System.AppDomain>类。
- 更好地支持与从中其他成员的数组一起使用<xref:System.Array>类。
- 更好地支持使用从中其他成员的特性<xref:System.Attribute>类。
- 更好地日历支持和其他格式设置选项<xref:System.DateTime>值。
- 其他<xref:System.Decimal>舍入功能。
- 中的其他功能<xref:System.Environment>类。
- 增强垃圾回收器通过控制<xref:System.GC>类。
- 对字符串比较、 枚举和中的标准化的增强支持<xref:System.String>类。
- 夏时制调整和中的过渡时间支持<xref:System.TimeZoneInfo.AdjustmentRule>和<xref:System.TimeZoneInfo.TransitionTime>类。
- 得到显著增强功能中的<xref:System.Type>类。
- 更好地支持通过添加具有的异常构造函数的异常对象的反序列化<xref:System.Runtime.Serialization.SerializationInfo>和<xref:System.Runtime.Serialization.StreamingContext>参数。

**.NET Framework 库的支持**

绝大多数库的目标.NET Framework 而不是.NET 标准。 但是，大部分这些库中的调用都是对.NET 标准 2.0 中包含的 Api。 从.NET 标准 2.0 开始，你可以访问.NET Framework 库从.NET 标准库通过使用[兼容性填充码](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification)。 此兼容性层是透明的开发人员;你无需执行任何操作即可利用.NET Framework 库。

单个的要求是必须.NET 标准 2.0 中包含的.NET Framework 类库所调用的 Api。

**适用于 Visual Basic 支持**

现在，你可以开发在 Visual Basic 中的标准.NET 库。 有关 Visual Basic 开发人员使用 Visual Studio 2017 版本 15.3 或更高版本与安装的.NET 核心工作负荷，Visual Studio 现在包含.NET 标准类库模板。 对于 Visual Basic 开发人员可以使用其他开发工具和环境，你可以使用[dotnet 新](../../core/tools/dotnet-new.md)命令以创建.NET 标准库项目。 有关详细信息，请参阅[工具支持的标准.NET 库](#tooling)。

<a name="tooling" />**对.NET 标准库工具支持**

对于版本的.NET 核心 2.0 和.NET 标准 2.0，这两个 Visual Studio 2017 和[.NET 核心命令行界面 (CLI)](../../core/tools/index.md)包括工具用于创建标准.NET 库的支持。 

如果在安装 Visual Studio 与**.NET 核心跨平台开发**工作负荷，你可以通过使用项目模板，如下图所示创建.NET 标准 2.0 库项目。 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![添加新.NET 标准库项目](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![添加新.NET 标准库项目](./media/std-project-vb.png)
---

如果你使用.NET 核心 CLI，以下[dotnet 新](../../core/tools/dotnet-new.md)命令创建一个类库项目面向.NET 标准 2.0。

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>另请参阅
[.NET 标准](../net-standard.md)
[引入.NET 标准](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
