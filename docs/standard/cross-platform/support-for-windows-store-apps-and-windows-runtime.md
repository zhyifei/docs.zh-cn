---
title: .NET Framework 对 Windows 应用商店应用程序和 Windows 运行时的支持情况
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a51d8d77318685e4a4c8b90a793f2946de4a792b
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025534"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>.NET Framework 对 Windows 应用商店应用程序和 Windows 运行时的支持情况
.NET Framework 4.5 支持多种与 Windows 运行时的软件开发方案。 这些方案分为三类：

- 开发[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]XAML 控件，如中所述的应用[路线图的 Windows 应用商店应用使用 C# 或 Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))，[如何 (XAML) tos](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))，和[.NET for Windows Store 应用概述](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- 开发类库以用于通过 .NET Framework 开发的 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用。

- 开发 Windows 运行时组件中打包。WinMD 文件，可由支持 Windows 运行时的任何编程语言。 有关示例，请参阅[C# 和 Visual Basic 中创建 Windows 运行时组件](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)。

 本主题概述了.NET Framework 提供了所有三个类别，并为 Windows 运行时组件中介绍的方案的支持。 第一个部分包含有关.NET Framework 和 Windows 运行时之间的关系的基本信息，并说明中的帮助系统和 IDE 可能会遇到的一些问题。 [第二部分](#WindowsRuntimeComponents)讨论开发 Windows 运行时组件的方案。

## <a name="the-basics"></a>基本知识
 .NET Framework 支持通过提供前面列出的三种开发方案[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]，并支持 Windows 运行时本身。

- [.NET framework 和 Windows 运行时命名空间](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces)提供的.NET Framework 类库的简化的视图，包括类型和成员可用于创建[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用和 Windows 运行时组件。

    - 当您使用 Visual Studio (Visual Studio 2012 或更高版本) 来开发[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用或 Windows 运行时组件中，一组引用程序集可确保您看到的相关类型和成员。

    - 此简化的 API 集简化了进一步的.NET Framework 中的重复或重复的 Windows 运行时功能删除的功能。 例如，它包含仅集合类型的泛型版本和 XML 文档对象模型被消除以支持 Windows 运行时 XML API 设置。

    - 只包装操作系统 API 的功能将被删除，因为 Windows 运行时可以轻松从托管代码调用。

     若要详细了解[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]，请参阅[.NET for Windows Store 应用概述](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))。 若要了解 API 选择过程，请参阅[适用于 Metro 风格的应用程序的.NET](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) .NET 博客中的条目。

- [Windows 运行时](/uwp/api/)提供用于生成用户界面元素[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用，并提供对操作系统功能的访问权限。 Windows 运行时和.NET Framework 一样具有元数据，使C#和 Visual Basic 编译器，以使用它们使用.NET Framework 的方式的 Windows 运行时类库。 .NET Framework 可以容易地使用某些差异隐藏的 Windows 运行时：

    - .NET Framework 和 Windows 运行时，例如用于添加和移除事件处理程序模式之间在编程模式的一些差异处于隐藏状态。 只需使用 .NET Framework 模式即可。

    - 隐藏在常用类型上存在一些差异（例如，基元类型和集合）。 只需使用.NET Framework 类型，如中所述[可见的差异在 IDE 中](#DifferencesVisibleInIDE)，这篇文章中更高版本。

 大多数情况下，.NET Framework 对 Windows 运行时的支持是透明的。 下一节讨论了一些托管的代码和 Windows 运行时之间的明显差异。

<a name="AboutReferenceDocumentation"></a>
### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>.NET Framework 和 Windows 运行时参考文档
 Windows 运行时和.NET Framework 文档集是独立的。 如果按 F1 显示关于类型或成员的帮助，将显示相应集合中的参考文档。 但是，如果你浏览[Windows 运行时引用](/uwp/api/)可能会遇到令人困惑的示例：

- 如主题<xref:Windows.Foundation.Collections.IIterable%601>接口不具有 Visual Basic 或 C# 的声明语法。 相反，在语法部分上方将显示一个注释 (在这种情况下，".NET:此接口显示为 System.Collections.Generic.IEnumerable\<T >")。 这是因为.NET Framework 和 Windows 运行时提供类似的功能与不同的接口。 此外，它们还有下列行为差异：`IIterable` 有一个 `First` 方法，而没有返回枚举器的 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 方法。 而不是强制你了解执行常见任务的不同的方式，.NET Framework 支持 Windows 运行时通过让托管的代码看起来可以使用熟悉的类型。 不会看到`IIterable`接口在 IDE 中，并因此将 Windows 运行时参考文档中遇到它的唯一方法是直接浏览该文档。

- <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)>文档阐释了一个紧密相关的问题：显示为不同的语言不同的参数类型。 对于 C# 和 Visual Basic，参数类型为 <xref:System.String?displayProperty=nameWithType> 和 <xref:System.Uri?displayProperty=nameWithType>。 同样，这是因为 .NET Framework 具有自己的 `String` 和 `Uri` 类型，并且，对于这种常用的类型，不宜强制 .NET Framework 用户了解执行操作的不同方式。 在 IDE 中，.NET Framework 隐藏相应的 Windows 运行时类型。

- 在少数情况下，如<xref:Windows.UI.Xaml.GridLength>结构，.NET Framework 提供了具有相同名称但功能更多的类型。 例如，有些构造函数和属性主题与 `GridLength` 相关，但是其语法部分仅适用于 Visual Basic 和 C#，因为成员仅在托管代码时是可用的。 在 Windows 运行时，结构具有只有字段。 Windows 运行时结构需要一个帮助器类<xref:Windows.UI.Xaml.GridLengthHelper>，若要提供等效的功能。 当你在编写托管代码时，不会在 IDE 中看到该帮助器类。

- 在 IDE 中，Windows 运行时类型似乎派生<xref:System.Object?displayProperty=nameWithType>。 它们看上去拥有从 <xref:System.Object> 继承的成员，例如 <xref:System.Object.ToString%2A?displayProperty=nameWithType>。 这些成员可正常如果类型的确继承自<xref:System.Object>，并在将 Windows 运行时类型转换为<xref:System.Object>。 此功能是.NET Framework 提供的 Windows 运行时支持的一部分。 但是，如果 Windows 运行时参考文档中查看的类型，会不出现任何此类成员。 <xref:System.Object?displayProperty=nameWithType> 参考文档为这些明显继承的成员提供了文档。

<a name="DifferencesVisibleInIDE"></a>
### <a name="differences-that-are-visible-in-the-ide"></a>可在 IDE 中看到的差异
 在更高级的编程方案，例如使用 Windows 运行时组件编写C#提供的应用程序逻辑[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]为 Windows 使用 JavaScript 生成的应用程序，这种差异很明显的表现还在 IDE 中为文档。 当组件返回`IDictionary<int, string>`到 JavaScript 中，并且您在 JavaScript 调试器中查看，可以看到的方法`IMap<int, string>`因为 JavaScript 使用 Windows 运行时类型。 下表显示了这两种语言中以不同方式显示的一些常用的集合类型：

|Windows 运行时类型|对应的 .NET Framework 类型|
|--------------------------------------------------------------|---------------------------------------|
|`IIterable<T>`|`IEnumerable<T>`|
|`IIterator<T>`|`IEnumerator<T>`|
|`IVector<T>`|`IList<T>`|
|`IVectorView<T>`|`IReadOnlyList<T>`|
|`IMap<K, V>`|`IDictionary<TKey, TValue>`|
|`IMapView<K, V>`|`IReadOnlyDictionary<TKey, TValue>`|
|`IBindableIterable`|`IEnumerable`|
|`IBindableVector`|`IList`|
|`Windows.UI.Xaml.Data.INotifyPropertyChanged`|`System.ComponentModel.INotifyPropertyChanged`|
|`Windows.UI.Xaml.Data.PropertyChangedEventHandler`|`System.ComponentModel.PropertyChangedEventHandler`|
|`Windows.UI.Xaml.Data.PropertyChangedEventArgs`|`System.ComponentModel.PropertyChangedEventArgs`|

 在 Windows 运行时，`IMap<K, V>`并`IMapView<K, V>`循环访问使用`IKeyValuePair`。 在将它们传递给托管代码时，它们显示为 `IDictionary<TKey, TValue>` 和 `IReadOnlyDictionary<TKey, TValue>`，因此自然要使用 `System.Collections.Generic.KeyValuePair<TKey, TValue>` 来枚举它们。

 接口在托管代码中的显示方式将影响实现这些接口的类型的显示方式。 例如， `PropertySet` 类实现 `IMap<K, V>`，后者在托管代码中显示为 `IDictionary<TKey, TValue>`。 `PropertySet` 显示为已实现 `IDictionary<TKey, TValue>` 而不是 `IMap<K, V>`，因此在托管代码中，它显示为具有 `Add` 方法，其行为类似于 .NET Framework 字典中的 `Add` 方法。 它不会显示为具有 `Insert` 方法。

 有关使用.NET Framework 创建 Windows 运行时组件和一个演练，演示如何与 JavaScript 一起使用此类组件的详细信息，请参阅[中创建 Windows 运行时组件C#和 Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>基元类型
 若要启用 Windows 运行时在托管代码中自然地使用，.NET Framework 基元类型而不是显示在代码中的 Windows 运行时基元类型。 在 .NET Framework 中，基元类型（如 `Int32` 结构）具有许多有用的属性和方法，如 `Int32.TryParse` 方法。 与此相反，基元类型和 Windows 运行时中的结构具有只有字段。 在托管代码中使用基元时，它们将显示为 .NET Framework 类型，您可以如往常一样使用 .NET Framework 类型的属性和方法。 以下列表提供了一个摘要：

- 对 Windows 运行时基元`Int32`， `Int64`， `Single`， `Double`， `Boolean`， `String` （Unicode 字符的不可变集合）， `Enum`， `UInt32`， `UInt64`，和`Guid`，可以使用类型中具有相同名称的`System`命名空间。

- 对于 `UInt8`，使用 `System.Byte`。

- 对于 `Char16`，使用 `System.Char`。

- 对于 `IInspectable` 接口，使用 `System.Object`。

- 对于 `HRESULT`，使用包含一个 `System.Int32` 成员的结构。

 与一样接口类型时，可能会看到这种表示形式的证据时，才在.NET Framework 项目使用的 Windows 运行时组件[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]通过 JavaScript 构建应用程序。

 其他基本的常用的 Windows 运行时类型中显示的托管代码，因为其.NET Framework 等效项包括`Windows.Foundation.DateTime`结构，在为托管代码中显示<xref:System.DateTimeOffset?displayProperty=nameWithType>结构，和`Windows.Foundation.TimeSpan`结构，其中将显示为<xref:System.TimeSpan?displayProperty=nameWithType>结构。

### <a name="other-differences"></a>其他差异
 在少数情况下，而不是 Windows 运行时类型在代码中显示.NET Framework 类型的事实需要您采取措施。 例如，<xref:Windows.Foundation.Uri?displayProperty=nameWithType>类显示为<xref:System.Uri?displayProperty=nameWithType>在.NET Framework 代码中。 <xref:System.Uri?displayProperty=nameWithType> 允许使用相对 URI，但<xref:Windows.Foundation.Uri?displayProperty=nameWithType>要求使用绝对 URI。 因此，在将 URI 传递给 Windows 运行时方法时，必须确保它是绝对。 (请参阅[向 Windows 运行时传递 URI](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)。)

<a name="WindowsRuntimeComponents"></a>
## <a name="scenarios-for-developing-windows-runtime-components"></a>开发的 Windows 运行时组件的方案
 托管 Windows 运行时组件支持的方案取决于下列一般原则：

- 使用.NET Framework 构建的 Windows 运行时组件已从其他 Windows Runtimelibraries 没有明显的差异。 例如，如果使用托管的代码重新实现本机 Windows 运行时组件的表面上是无法区分两个组件。 在托管代码中编写的组件对使用它的代码来说是不可见的，即使该代码本身是托管代码。 但是，在内部，组件是真正的托管代码并运行在公共语言运行时 (CLR) 上。

- 组件可以包含实现应用程序逻辑和/或 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] UI 控件的类型。

    > [!NOTE]
    >  最好将 UI 元素与应用程序逻辑分离开来。 此外，在使用 JavaScript 和 HTML 为 Windows 编写的 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用中，不能使用 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] UI 控件。

- 组件可以是用于 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用的 Visual Studio 解决方案中的一个项目，也可以是一个可添加到多个解决方案中的可重用组件。

    > [!NOTE]
    >  如果你的组件将仅与使用C#或 Visual Basic 中，没有理由以使其成为 Windows 运行时组件。 如果您改为使得其普通的.NET Framework 类库，您无需将其公共 API 图面限制为 Windows 运行时类型。

- 你可以通过使用 Windows 运行时释放的可重用的组件版本<xref:Windows.Foundation.Metadata.VersionAttribute>属性标识的类型 （以及类型中的成员） 添加不同的版本。

- 在组件中的类型可以从 Windows 运行时类型派生。 控件可派生中的基元控件类型<xref:Windows.UI.Xaml.Controls.Primitives>命名空间或者从多个完成控件如<xref:Windows.UI.Xaml.Controls.Button>。

    > [!IMPORTANT]
    >  从开始[!INCLUDE[win8](../../../includes/win8-md.md)]和.NET Framework 4.5 中，托管的 Windows 运行时组件中的所有公共类型必须密封。 另一个 Windows 运行时组件中的类型不能从它们派生。 如果要在组件中提供多态行为，可以创建一个接口并在多态类型中实现它。

- 在组件中的公共类型上的所有参数和返回类型必须都是 Windows 运行时类型 （包括组件定义的 Windows 运行时类型）。

 以下部分提供常见方案的示例。

### <a name="application-logic-for-a-includewin8appnamelongincludeswin8-appname-long-mdmd-app-with-javascript"></a>使用 JavaScript 生成的 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用的应用程序逻辑
 在使用 JavaScript 为 Windows 开发 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用时，你可能会发现，应用程序逻辑的某些部分在托管代码中性能更佳或更易于开发。 JavaScript 不能直接使用 .NET Framework 类库，但是，您可以使将类库包装为 .WinMD 文件。 在此方案中，Windows 运行时组件是应用程序中的重要组成部分，因此不宜提供版本特性。

### <a name="reusable-includewin8appnamelongincludeswin8-appname-long-mdmd-ui-controls"></a>可重用的 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] UI 控件
 您可以打包一组可重用的 Windows 运行时组件中相关用户界面控件。 该组件可以独立销售，或作为您创建的应用元素使用。 在此方案中，则最好使用 Windows 运行时<xref:Windows.Foundation.Metadata.VersionAttribute>属性增强兼容性。

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>来自现有 .NET Framework 应用的可重用的应用程序逻辑
 作为独立的 Windows 运行时组件，可以从现有桌面应用程序打包托管的代码。 这样即可将该组件用于由 C++ 或 JavaScript 生成的 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用以及由 C# 或 Visual Basic 生成的 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用。 如果代码有多个可重用的方案，可选择进行版本控制。

## <a name="related-topics"></a>相关主题

|Title|描述|
|-----------|-----------------|
|[适用于 Microsoft Store 应用的 .NET 概述](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|描述.NET Framework 类型和成员可用于创建[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用和 Windows RuntimeComponents。 （位于 Windows 开发中心。）|
|[使用 C# 或 Visual Basic Windows 应用商店应用的路线图](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|提供关键资源来帮助您开始使用 C# 或 Visual Basic 开发 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用，这些资源包括许多快速入门主题、教程和最佳做法。 （位于 Windows 开发中心。）|
|[如何 tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|提供关键资源来帮助您开始使用 C# 或 Visual Basic 开发 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用，这些资源包括许多快速入门主题、教程和最佳做法。 （位于 Windows 开发中心。）|
|[用 C# 和 Visual Basic 创建 Windows 运行时组件](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|介绍如何创建使用.NET Framework 的 Windows 运行时组件，解释了如何使用它作为的一部分[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用为 Windows 使用 JavaScript、 生成并介绍了如何调试使用 Visual Studio 的组合。 （位于 Windows 开发中心。）|
|[Windows 运行时引用](/uwp/api/)|Windows 运行时参考文档。 （位于 Windows 开发中心。）|
|[向 Windows 运行时传递 URI](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|介绍了将 URI 从托管代码传递到 Windows 运行时，以及如何避免它时可能出现的问题。|
