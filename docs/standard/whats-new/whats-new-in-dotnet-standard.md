---
title: ".NET Standard 中的新增功能"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3a5833bdfcf1e3433ea82403908e9a06a88cde27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-the-net-standard"></a>.NET Standard 中的新增功能

.NET Standard 是一种正式规范，定义了一组版本化 API，这些 API 必须可用于符合相应 Standard 版本要求的 .NET 实现。 .NET Standard 面向库开发者。 定目标到 .NET Standard 版本的库可用于任意 .NET Framework、.NET Core 或支持 Standard 版本的 Xamarin 实现。

.NET Standard 的最新版本是 2.0。 .NET Core 2.0 SDK 及已安装 .NET Core 工作负载的 Visual Studio 2017 版本 15.3 包含它。

## <a name="supported-net-implementations"></a>支持的 .NET 实现

以下 .NET 实现支持 .NET Standard 2.0：

- .NET Core 2.0
- .NET Framework 4.6.1
- Mono 5.4
- Xamarin.iOS 10.14
- Xamarin.Mac 3.8
- Xamarin.Android 8.0
- 通用 Windows 平台 10.0.16299

## <a name="whats-new-in-the-net-standard-20"></a>.NET Standard 2.0 中的新增功能
 
.NET Standard 2.0 新增了以下功能：

**大幅扩展了 API 集**

.NET Standard 版本 1.6 中包含了相对较小的一部分 API。 不包含的 API 许多都是 .NET Framework 或 Xamarin 中的常用 API。 这样一来，开发变得更为棘手，因为开发人员必须在开发定目标到多个 .NET 实现的应用和库时，寻找常用 API 的合适替代项。 为了消除此限制，.NET Standard 2.0 向 Standard 旧版本 .NET Standard 1.6 中的可用 API 补充了 20,000 多个 API。 有关添加到 .NET Standard 2.0 的 API 列表，请参阅 [.NET Standard 2.0 与 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md)。 

.NET Standard 2.0 的 <xref:System> 命名空间中新增的一些功能包括：

- 支持 <xref:System.AppDomain> 类。
- 更好地支持通过 <xref:System.Array> 类中的附加成员处理数组。
- 更好地支持通过 <xref:System.Attribute> 类中的附加成员处理属性。
- 改进了日历支持，并附加了 <xref:System.DateTime> 值的格式设置选项。
- 附加了 <xref:System.Decimal> 舍入功能。
- 在 <xref:System.Environment> 类中附加了功能。
- 增强了通过 <xref:System.GC> 类控制垃圾回收器。
- 增强了 <xref:System.String> 类中的字符串比较、枚举和规范化支持。
- <xref:System.TimeZoneInfo.AdjustmentRule> 和 <xref:System.TimeZoneInfo.TransitionTime> 类支持夏令时调整和时间转换。
- 显著改进了 <xref:System.Type> 类中的功能。
- 通过添加包含 <xref:System.Runtime.Serialization.SerializationInfo> 和 <xref:System.Runtime.Serialization.StreamingContext> 参数的异常构造函数，改进了对异常对象反串行化的支持。

**支持 .NET Framework 库**

绝大多数库定目标到 .NET Framework，而不是 .NET Standard。 不过，这些库大多调用的是 .NET Standard 2.0 中的 API。 自 .NET Standard 2.0 起，可以使用[兼容性垫片](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification)从 .NET Standard 库访问 .NET Framework 库。 此兼容性层对开发人员透明；无需执行任何操作，即可使用 .NET Framework 库。

只有一项要求就是，.NET Framework 类库调用的 API 必须是 .NET Standard 2.0 中的 API。

**支持 Visual Basic**

现在可以使用 Visual Basic 开发 .NET Standard 库。 如果 Visual Basic 开发人员使用的是已安装 .NET Core 工作负载的 Visual Studio 2017 版本 15.3 或更高版本，现在可以使用 Visual Studio 中的 .NET Standard 类库模板。 对于使用其他开发工具和环境的 Visual Basic 开发人员，可以使用 [dotnet new](../../core/tools/dotnet-new.md) 命令创建 .NET Standard 库项目。 有关详细信息，请参阅 [.NET Standard 库的工具支持](#tooling)。

<a name="tooling" />**.NET Standard 库的工具支持**

随着 .NET Core 2.0 和 .NET Standard 2.0 发布，Visual Studio 2017 和 [.NET Core 命令行接口 (CLI)](../../core/tools/index.md) 均包含创建 .NET Standard 库所需的工具支持。 

如果安装带 .NET Core 跨平台开发工作负载的 Visual Studio，可以使用项目模板创建 .NET Standard 2.0 库项目，如下图所示。 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![添加新的 .NET Standard 库项目](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![添加新的 .NET Standard 库项目](./media/std-project-vb.png)
---

如果使用的是 .NET Core CLI，可以使用下面的 [dotnet new](../../core/tools/dotnet-new.md) 命令，创建定目标到 .NET Standard 2.0 的类库项目。

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>请参阅
[.NET Standard](../net-standard.md)
[.NET Standard 简介](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
