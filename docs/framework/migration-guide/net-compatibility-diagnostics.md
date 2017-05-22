---
title: ".NET 兼容性诊断 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: twsouthwick
ms.author: tasou
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 06ebf87e02c8fd745d9c2f3a55eca329323a7d91
ms.contentlocale: zh-cn
ms.lasthandoff: 05/22/2017

---
# <a name="net-compatibility-diagnostics"></a>.NET 兼容性诊断
.NET 兼容性诊断是 Roslyn 提供技术支持的分析器，有助于确定 .NET Framework 不同版本之间的应用程序兼容性问题。 此列表包含所有可用的分析器，尽管仅部分分析器适用于任何具体的迁移。 这些分析器可确定计划迁移会发生的问题，并仅显示这些问题。 对于因版本受影响而分裂出来的问题，请参阅：[应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility.md)。  
  
 每个问题包含以下信息：  
  
-   从以前版本发生的更改的介绍。  
  
-   建议介绍了更改如何影响客户，以及是否有任何解决办法可以保持各个版本之间的兼容性。  
  
-   对于更改重要性的评估。 应用程序兼容性问题可分成以下几类：  
  
    |||  
    |-|-|  
    |主要|影响大量应用或需要修改大量代码的重大更改。|  
    |次要|影响少量应用或需要修改少量代码的更改。|  
    |边缘情况|在极少数特定的情况下影响应用的更改。|  
    |透明|对应用程序开发人员或用户没有明显影响的更改。|  
  
-   版本指示了更改首次出现在框架中的时间。 某些更改将会还原，这也会有所指示。  
  
-   更改类型：  
  
    |||  
    |-|-|  
    |重定目标|更改会影响重新编译以面向新版 .NET Framework 的应用。|  
    |运行时|更改会影响面向以前版本的 .NET Framework 但在更高版本上运行的现有应用。|  
  
-   受影响的 API（如果有）。  
  
-   可用诊断的 ID  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1：SoapFormatter 无法反序列化哈希表和类似有序的集合对象  
  
|||  
|-|-|  
|详细信息|SoapFormatter 不保证在一个 .NET Framework 版本下进行序列化的对象能够在其他版本下成功反序列化。 具体而言，某些有序集合（例如哈希表）已在 4.0 和 4.5 中添加了成员，如果这些类型的对象在 .NET 4.5 中进行了序列化，它们在 .NET 4.0 中将无法反序列化。 请注意，如果序列化的数据在同一 .NET Framework 版本中进行序列化和反序列化，将不会发生任何问题。|  
|建议|SoapFormatter 序列化应替换为 BinaryFormatter 序列化或 NetDataContractSerialization，才能应对 .NET Framework 更改。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|分析器|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3：WPF DataTemplate 元素现在对 UIA 可见  
  
|||  
|-|-|  
|详细信息|以前 DataTemplate 元素对 UI 自动化不可见。 从 4.5 开始，UI 自动化将能检测到这些元素。 这在许多情况下很有用，但可能会中断依赖于不包含 DataTemplate 元素的 UIA 树的测试。|  
|建议|此应用的 UI 自动化测试需要更新，以便考虑到 UIA 树现在所包含的以前不可见的 DataTemplate 元素。 例如，对于预计某些元素彼此相邻的测试，现在需要考虑到其间之前不可见的 UIA 元素。 否则，依赖 UIA 元素的特定计数或索引的测试可能需要使用新值进行更新。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|分析器|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4：WPF 文本框选定文本在文本框处于非活动状态时，将显示其他颜色  
  
|||  
|-|-|  
|详细信息|在 .NET 4.5 中，当 WPF 文本框控件处于非活动状态（该控件没有焦点）时，文本框中选定文本所显示的颜色与该控件处于活动状态时所显示的颜色不同。|  
|建议|以前的 (.NET 4.0) 行为可通过将 [FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx) 属性设为 false 来还原。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|分析器|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5：List\<T>.ForEach 在修改列表项时可能会引发异常  
  
|||  
|-|-|  
|详细信息|从 .NET 4.5 开始，如果修改了调用集合中的元素，`List<T>.ForEach` 枚举器将引发 InvalidOperationException 异常。 该操作在以前不会引发异常，但可能会导致争用条件。|  
|建议|理想情况下，应修复代码以便在枚举列表元素时不会修改列表，因为这始终不是安全操作。 但是，若要还原到以前行为，应用可以面向 .NET 4.0。|  
|范围|边缘|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 API|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|分析器|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6：System.Uri 分析遵守 RFC 3987  
  
|||  
|-|-|  
|详细信息|URI 分析在 .NET 4.5 中做了几方面的更改。 但请注意，这些更改仅影响面向 .NET 4.5 的代码。 如果二进制文件面向 .NET 4.0，将遵守旧行为。 .NET 4.5 中对 URI 分析所做的更改包括：<br /><br /> URI 分析将根据 RFC 3987 中的最新 IRI 规则执行规范化和字符检查<br /><br /> 将仅对 URI 的主机部分执行 Unicode 范式 C<br /><br /> 无效的 mailto: URI 现在会引发异常<br /><br /> 现在将保留路径段末尾的尾随点<br /><br /> `file://` URI 不会转义 `?` 字符<br /><br /> 不支持从 `U+0080` 到 `U+009F` 的 Unicode 控制字符<br /><br /> 逗号字符 `,` 或 `%2c` 不会自动取消转义|  
|建议|如果需要使用旧的 .NET 4.0 URI 分析语义（通常不需要），可通过面向 .NET 4.0 使用它们。 这可通过在程序集上使用 TargetFrameworkAttribute 来实现，也可以通过“项目属性”页中 Visual Studio 的项目系统 UI 来实现。|  
|范围|主要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 API|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|分析器|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10：System.Uri 转义现在支持 RFC 3986 (http://tools.ietf.org/html/rfc3986)  
  
|||  
|-|-|  
|详细信息|URI 转义在 .NET 4.5 中做了更改，以支持 [RFC 3986](http://tools.ietf.org/html/rfc3986)。 具体更改包括：<br /><br /> `EscapeDataString` 根据 RFC 3986 转义保留字符。<br /><br /> `EscapeUriString` 未转义保留字符。<br /><br /> 如果 `UnescapeDataString` 遇到无效的转义序列，则它不会引发异常。<br /><br /> 未保留的转义字符已取消转义。|  
|建议|更新应用程序，以便在出现无效转义序列时不依赖于要引发 UnescapeDataString。 此类序列现在必须直接进行检测。<br /><br /> 同样，预计转义和非转义 URI 和数据字符串在 .NET 4.0 和 .NET 4.5 中可能会有所不同，并且这些字符串不应直接在各种 .NET 版本中进行比较。 而在对这些字符串进行任何比较前，应在单个 .NET 版本中对其进行分析和规范化。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|分析器|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11：System.Net.PeerToPeer.Collaboration 在 Windows 8 上不可用  
  
|||  
|-|-|  
|详细信息|System.Net.PeerToPeer.Collaboration 命名空间在 Windows 8 或更高版本上不可用。|  
|建议|支持 Windows 8 或更高版本的应用必须进行更新，才能不依赖于此命名空间或其成员。|  
|范围|主要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|分析器|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12：MEF 目录实现 IEnumerable，因此不能再用于创建序列化程序  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.5 开始，MEF 目录实现 IEnumerable，因此不能再用于创建序列化程序（XmlSerializer 对象）。 尝试对 MEF 目录进行序列化会引发异常。|  
|建议|不能再使用 MEF 创建序列化程序|  
|范围|主要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13：在 4.0 行为中缺少了目标框架名字对象结果  
  
|||  
|-|-|  
|详细信息|未在程序集级别应用 [TargetFrameworkAttribute](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) 的应用程序将通过使用 .NET Framework 4.0 的语义 (quirks) 自动运行。 为了确保高质量，建议所有二进制文件均通过 TargetFrameworkAttribute 显式属性化，以指示用于生成它们的 .NET Framework 版本。 请注意，在项目文件中使用目标框架名字对象将使 MSBuild 自动应用 TargetFrameworkAttribute。|  
|建议|应通过以下方法提供[目标框架属性](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx)：将该属性直接添加至程序集，或者在[项目文件中或通过 Visual Studio 的项目属性 GUI](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx) 指定目标框架。|  
|范围|主要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14：无法再将 EnableViewStateMac 设为 false  
  
|||  
|-|-|  
|详细信息|ASP.NET 不再允许开发者指定 `<pages enableViewStateMac="false"/>` 或 `<@Page EnableViewStateMac="false" %>`。 现在，针对所有带嵌入视图状态的请求强制执行视图状态消息身份验证代码 (MAC)。 仅影响将 EnableViewStateMac 属性显式设置为 false 的应用。|  
|建议|EnableViewStateMac 必须假设为 true，并且必须解决任何生成的 MAC 错误（如[本指南](https://support.microsoft.com/kb/2915218)所述，该指南包含多种解决方法，具体视引发 MAC 错误的具体原因而定）。|  
|范围|主要|  
|版本|4.5.2|  
|类型|运行时|  
|分析器|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18：BlockingCollection\<T>.TryTakeFromAny 不会再引发任何异常  
  
|||  
|-|-|  
|详细信息|如果其中一个输入集合标记为已完成，则 `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)` 不会再返回 -1，`BlockingCollection<T>.TakeFromAny` 也不会再引发异常。 当其中一个集合为空或已完成，但其他集合仍具有可检索的项时，可通过此更改来使用这些集合。|  
|建议|如果在阻止集合已完成的情况下，在 TryTakeFromAny 返回 -1 或 TakeFromAny 引发异常时用于控制流，此类代码现在应改为使用 `.Any(b => b.IsCompleted)` 检测该条件。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|分析器|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19：XmlSchemaException 现在可以正确设置行位置  
  
|||  
|-|-|  
|详细信息|如果已将 LoadOptions.SetLineInfo 值传递到 Load 方法，并发生验证错误，XmlSchemaException.LineNumber 和 XmlSchemaException.LinePosition 属性现在将包含行信息。|  
|建议|应该对假设不设置 XmlSchemaException.LineNumber 和 XmlSchemaException.LinePosition 的异常处理代码进行更新，因为现在加载 XML 的同时使用 SetLineInfo 可以正确设置这些属性。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|分析器|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20：System.Activities 现在是 APTCA  
  
|||  
|-|-|  
|详细信息|该程序集已使用 AllowPartiallyTrustedCallersAttribute 属性进行标记。|  
|建议|无法使用 SecurityCriticalAttribute 标记派生类。 以前，派生类型必须使用 SecurityCriticalAttribute 进行标记。 但是，此更改不应有实际影响。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21：工作流 3.0 类型已过时  
  
|||  
|-|-|  
|详细信息|Windows Workflow Foundation (WWF) 3.0 API（来自于 System.Workflow 命名空间）现已过时。|  
|建议|应改用新的 WWF 4.0 API（在 System.Activities 中）。 可在[此处](https://msdn.microsoft.com/library/jj205427.aspx)找到使用新 API 的示例，[此处](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx)还提供更深入的指导。 或者，由于仍然支持 WWF 3.0 API，因此可能会使用它们，通过禁止显示生成时警告或使用较旧的编译器可以避免出现该警告。|  
|范围|主要|  
|版本|4.5|  
|类型|重定目标|  
|分析器|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22：某些工作流拖放 API 已过时  
  
|||  
|-|-|  
|详细信息|此工作流拖放 API 已过时，如果针对 4.5 重新生成应用，将引发编译器警告。|  
|建议|应改用支持包含多个对象的操作的新 [DragDropHelper](https://msdn.microsoft.com/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx) API。 或者，可以禁止显示生成警告，也可以使用较早的编译器避免出现此类警告。 API 仍受支持。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 API|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|分析器|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23：新的（不明确的）Dispatcher.Invoke 重载可能会导致不同行为  
  
|||  
|-|-|  
|详细信息|.NET Framework 4.5 向 Dispatcher.Invoke 添加了新重载，它们包含 System.Action 类型的一个参数。 在重新编译现有代码时，编译器可能将对具有 Delegate 参数的 Dispatcher.Invoke 方法的调用解析为对具有 System.Action 参数的 Dispatcher.Invoke 方法的调用。 如果将对具有 Delegate 参数的 Dispatcher.Invoke 重载的调用解析为对具有 System.Action 参数的 Dispatcher.Invoke 重载的调用，可能出现以下行为差异：<br /><br /> 如果发生异常，将不会引发 Dispatcher.UnhandledExceptionFilter 和 Dispatcher.UnhandledException 事件。 相反，异常将由 UnobservedTaskException 事件处理。<br /><br /> 对某些成员（如 DispatcherOperation.Result）的调用会受阻，直到操作完成。|  
|建议|若要避免出现多义性（以及异常处理或阻止行为中可能出现的差异），调用 Dispatcher.Invoke 的代码可传递空 object[] 作为 Invoke 调用的第二个参数，确保解析为 .NET 4.0 方法重载。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 API|<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|分析器|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24：EncoderParameter ctor 已过时  
  
|||  
|-|-|  
|详细信息|`EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` 构造函数现已过时，使用它将引发生成警告。|  
|建议|虽然 `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` 构造函数仍将继续运行，但应改用以下构造函数，以避免在使用 .NET 4.5 工具重新编译代码时出现已过时生成警告：[EncoderParameter.EncoderParameter(Encoder, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/library/hh875096\(v=vs.110\).aspx)。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 API|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|分析器|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26：带有超时自变量的 Task.WaitAll 方法的行为更改  
  
|||  
|-|-|  
|详细信息|Task.WaitAll 行为在 .NET 4.5 中变得更加一致。<br /><br /> 在 .NET Framework 4 中，这些方法的行为不一致。 当超时到期时，如果在调用此方法之前已完成或已取消一个或多个任务，则此方法会引发 AggregateException 异常。 在超时到期时，如果在调用此方法之前尚未完成或取消任何任务，但在调用此方法之后，一个或多个任务进入了这些状态，则该方法返回 false。<br />在 .NET Framework 4.5 中，如果在超时时间间隔到期时仍有任务在运行，这些方法重载现在将返回 false；仅当取消某个输入任务（无论是在方法调用之前还是之后取消）且没有任务仍在运行时，它们将引发 AggregateException 异常。|  
|建议|如果 AggregateException 已捕获作为检测在调用 WaitAll 之前已取消的任务的方法，该代码应通过 IsCanceled 属性（例如：.Any(t => t.IsCanceled)）执行相同的检测操作，因为 .NET 4.6 仅当所有等待任务在超时前均已完成时才会引发。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|分析器|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27：数据定义语言 (DDL) API 行为的更改  
  
|||  
|-|-|  
|详细信息|指定 AttachDBFilename 时，DDL API 的行为已更改，具体如下：<br /><br /> 连接字符串不需要指定 Initial Catalog 值。 以前，需要 AttatchDBFilename 和 Initial Catalog。<br /><br /> 如果指定了 AttatchDBFilename 和 Initial Catalog，并且存在给定的 MDF 文件，ObjectContext.DatabaseExists 方法将返回 true。 以前，它会返回 false。<br /><br /> 如果指定了 AttatchDBFilename 和 Initial Catalog，并且存在给定的 MDF 文件，则调用 ObjectContext.DeleteDatabase 方法会删除文件。<br /><br /> 如果在连接字符串指定某个 AttachDBFilename 值，且不存在 MDF 和 Initial Catalog 时调用 ObjectContext.DeleteDatabase，该方法将引发 InvalidOperationException 异常。 以前，它会引发 SqlException 异常。|  
|建议|利用这些更改，可以更轻松地生成使用 DDL API 的工具和应用程序。 这些更改会影响以下方案中的应用程序兼容性：<br /><br /> 如果 ObjectContext.DatabaseExists 返回 true，用户将编写直接执行 DROP DATABASE 命令的代码，而不是调用 ObjectContext.DeleteDatabase。 如果未附加数据库但存在 MDF 文件，则会中断现有代码。<br /><br /> 用户编写希望 ObjectContext.DeleteDatabase 方法在 Initial Catalog 和 MDF 文件不存在时引发 SqlException 异常而非 InvalidOperationException 异常的代码。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28：MachineKey.Encode 和 MachineKey.Decode 方法现已过时  
  
|||  
|-|-|  
|详细信息|这些方法现在已过时。 调用这些方法的代码编译会产生编译器警告。|  
|建议|推荐的备选项是 [MachineKey.Protect](https://msdn.microsoft.com/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) 和 [MachineKey.Unprotect](https://msdn.microsoft.com/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx)。 或者，可以禁止显示生成警告，也可以使用较早的编译器避免出现此类警告。 API 仍受支持。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 API|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> <xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|分析器|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29：默认情况下，禁用 OData URL 中的 Replace 方法  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.5 开始，默认会禁用 OData URL 中的 Replace 方法。 在禁用 OData Replace 时（现在是默认设置），任何包含 replace 函数的用户请求（这并不常见）都将失败。|  
|建议|如果需要 replace 方法（这并不常见），可通过[配置设置](https://msdn.microsoft.com/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx)重新启用。 但是，启用的 replace 方法可能会带来安全漏洞，应仅在仔细检查后使用。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|分析器|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30：System.ServiceModel.Web.WebServiceHost 对象不再添加默认终结点  
  
|||  
|-|-|  
|详细信息|如果显式终结点已由应用程序代码添加，则 System.ServiceModel.Web.WebServiceHost 对象不再添加默认终结点。|  
|建议|如果用户希望能够连接到默认终结点，并且其他显式终结点已添加到 WebServiceHost，则还应显式添加默认终结点（使用 AddDefaultEndpoints）。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|分析器|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31：EventSource.WriteEvent impls 必须传递它接收的相同参数 WriteEvent（以及 ID）  
  
|||  
|-|-|  
|详细信息|运行时现在强制执行用于指定以下内容的协定：从 EventSource 派生的用于定义 ETW 事件方法的类必须使用事件 ID（后跟 ETW 事件方法已传递的相同自变量）调用基类 EventSource.WriteEvent 方法。|  
|建议|如果 EventListener 在处理违反此协定的事件源过程中读取 EventSource 数据，将引发 IndexOutOfRangeException 异常。|  
|范围|次要|  
|版本|4.5.1|  
|类型|运行时|  
|分析器|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32：现在需要遵守 MinFreeMemoryPercentageToActiveService  
  
|||  
|-|-|  
|详细信息|此设置可确立激活 WCF 服务之前必须在服务器上可用的最小内存。 它的目的是阻止 OutOfMemoryException 异常发生。 在 .NET Framework 4.5 中，此设置没有效果。 在 .NET Framework 4.5.1 中，观察到该设置。|  
|建议|如果 Web 服务器上的可用内存少于由配置设置定义的百分比，将引发异常。 某些成功启动并且在受约束的内存环境中运行的 WCF 服务现在可能失败。|  
|范围|次要|  
|版本|4.5.1|  
|类型|运行时|  
|分析器|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33：XmlTextReader DTD 实体扩展限制为 10,000,000 个字符  
  
|||  
|-|-|  
|详细信息|DTD 实体扩展现在限制为 10,000,000 个字符。 加载不带 DTD 实体扩展或带有限的 DTD 实体扩展的 XML 文件不受影响。 包含了扩展到 10,000,000 个字符以上的 DTD 实体的文件将无法加载，且会立即引发异常。|  
|建议|如果 DTD 实体扩展的限制低于 10,000,000，该值可使用 [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx) 属性重写。 可将包括相应的 MaxCharactersFromEntity 值的 XmlReaderSettings 传递到 [XmlReader.Create](https://msdn.microsoft.com/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx)|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|分析器|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35：XSLT 样式表异常消息已更改  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.5 中，XSLT 文件过于复杂时显示的错误消息的文本为“样式表太复杂”。 在早期版本中，错误消息为“XSLT 编译错误”。 取决于错误消息的文本的应用程序代码将不再有效。 但是，异常类型保持不变，因此，此更改应该不会造成实际影响。|  
|建议|根据此错误条件发出的异常消息更新任何应用代码，以收到新消息，或者（最好是）更新代码以仅依赖于未更改的异常类型 ([XsltException](https://msdn.microsoft.com/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx))。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|分析器|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36：WF 现在采用不同方式序列化 Expressions.Literal\<T> DateTimes（中断自定义 XAML 分析器）  
  
|||  
|-|-|  
|详细信息|关联的 [ValueSerializer](https://msdn.microsoft.com/library/system.windows.markup.valueserializer\(v=vs.110\).aspx) 对象将转换 DateTime 或 DateTimeOffset 对象，它们的秒和毫秒部分均为非零值，并且（对于 DateTime 值）DateTime.Kind 属性已指定为属性元素语法而非字符串。 此更改允许 DateTime 和 DateTimeOffset 值往返。 假定输入 XAML 是采用特性语法的自定义 XAML 分析器将无法正常运行。|  
|建议|此更改允许 DateTime 和 DateTimeOffset 值往返。 假定输入 XAML 是采用特性语法的自定义 XAML 分析器将无法正常运行。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37：WPF PageRangeSelection 中的新枚举值  
  
|||  
|-|-|  
|详细信息|已向 [PageRangeSelection](https://msdn.microsoft.com/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx) 枚举添加了两个新成员（CurrentPage 和 SelectedPage）。|  
|建议|大多数情况下，这些更改不会影响用户代码。 但应修改依赖特定数量的元素的代码，这些元素存在于 PageRangeSelection 类型上的 Enum.GetNames 或 Enum.GetValues 调用中。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|分析器|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38：WPF DispatcherSynchronizationContext.CreateCopy 现在返回新副本，而非当前实例  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4 中，DispatcherSynchronizationContext.CreateCopy() 返回当前实例的引用，这主要作为一项性能优化。 在 .NET Framework 4.5 中，它返回新实例，这可以首次得出结论：相同的引用指示执行线程位于正确的同步上下文中。  检查这些引用标识的代码可能不受影响，但由于此更改，作为迁移到 .NET Framework 4.5 或更高版本的一部分，应测试调用 DispatcherSynchronizationContext.CreateCopy 的代码。|  
|建议|请注意，DispatcherSynchronizationContext.CreateCopy() 现在将返回新的 SynchronizationContext 对象。  以前，使用按此方法所生成引用的等效项的代码实际上不会检查它是否在正确的上下文中，但针对 .NET 4.5 或更高版本生成时则会检查。  虽然不太可能产生问题，但执行受影响的代码路径应足以确定这是否会带来任何问题。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|分析器|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39：释放对象后，System.Threading.Tasks.Task 不再引发 ObjectDisposedException  
  
|||  
|-|-|  
|详细信息|除 Task.IAsyncResult.AsyncWaitHandle 之外，释放对象后，System.Threading.Tasks.Task 方法不再引发 ObjectDisposedException 异常。<br />此更改支持缓存任务的使用。 例如，方法会返回一个缓存任务来表示已完成的操作，而不是分配新任务。 在以前的 .NET Framework 版本中无法执行此操作，因为任务的任何使用者都可以处置它（呈现为不可用）。|  
|建议|请注意，如果释放对象，Task 方法可能不再引发 ObjectDisposedExceptions。 如果某个应用依靠此异常了解任务是否已释放，应对其进行更新以使用 [Task.Status](https://msdn.microsoft.com/library/system.threading.tasks.task.status\(v=vs.110\).aspx) 显式检查任务状态。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40：ObjectContext.CreateDatabase 和 DbProviderServices.CreateDatabase 方法处理异常的方式不同  
  
|||  
|-|-|  
|详细信息|从 .NET 4.5 开始，如果数据库创建失败，`CreateDatabase` 方法将尝试删除空数据库。 如果该操作成功，将传播原始 `SQLException`（而非始终在 .NET 4.0 中引发的 `InvalidOperationException`）|  
|建议|如果在执行 ObjectContext.CreateDatabase 或 DbProviderServices.CreateDatabase 时捕获 InvalidOperationException，现在还应捕获 SQLExceptions。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|分析器|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41：ObjectContext.Translate 和 ObjectContext.ExecuteStoreQuery 现在支持枚举类型  
  
|||  
|-|-|  
|详细信息|在 .NET 4.0 中，`ObjectContext.Translate` 和 `ObjectContext.ExecuteStoreQuery` 方法的泛型参数 `T` 不能是枚举类型。 现在支持这种情况。|  
|建议|如果在 .NET 4.0 的枚举类型上调用了 Translate 或 ExecuteStoreQuery，则返回“0”。 如果需要该行为，调用应替换为常数 0（或其枚举等效项）。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|分析器|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42：Enumerable.Empty\<TResult> 始终返回缓存的实例  
  
|||  
|-|-|  
|详细信息|从 .NET 4.5 开始，`Enumerable.Empty` 始终返回缓存的内部实例 `IEnumerable<T>`。<br /><br /> 以前，在调用 API 时，`Enumerable.Empty` 将缓存空 `IEnumerable<T>`，这意味着在同时快速调用 `Enumerable.Empty` 的某些情况下，针对 API 的不同调用将返回不同的类型实例。|  
|建议|因为以前的行为不确定，所以代码不太可能依赖它。 但是，如果出现需要比较空枚举并希望它们有时不相等这一罕见情形，应创建显式空数组 (`new T[0]`)，而非使用 `Enumerable.Empty`。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|分析器|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43：HttpRequest.ContentEncoding 属性禁止使用 UTF7  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.5 开始，HttpRequests 正文禁止使用 UTF-7 编码。 在某些情况下，取决于传入的 UTF-7 数据的应用程序数据将不会正确解码。|  
|建议|理想情况下，应更新应用程序，使其在 HttpRequests 中不使用 UTF-7 编码。 或者，可以使用 [appSettings](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx) 元素的 `aspnet:AllowUtf7RequestContentEncoding` 属性还原旧行为。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|分析器|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44：HttpUtility.JavaScriptStringEncode 转义 & 号  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.5 开始，JavaScriptStringEncode 转义 & 号 (&) 字符。|  
|建议|如果应用依赖于此方法以前的行为，可将 aspnet:JavaScriptDoNotEncodeAmpersand 设置添加到配置文件中的 [ASP.NET appSettings 元素](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx)。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|分析器|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46：EventListener 将截断带有嵌入 null 的字符串  
  
|||  
|-|-|  
|详细信息|EventListener 将截断带有嵌入 null 的字符串。 空字符不受 EventSource 类支持。 此更改仅影响使用 EventListener 读取进程中 EventSource 数据的应用以及使用空字符作为分隔符的应用。|  
|建议|应可能更新 EventSource 数据，以便不使用嵌入的空字符。|  
|范围|边缘|  
|版本|4.5.1|  
|类型|运行时|  
|受影响的 API|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName>|  
|分析器|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48：ObsoleteAttribute 在 WinMD 方案中导出为 ObsoleteAttribute 和 DeprecatedAttribute  
  
|||  
|-|-|  
|详细信息|在创建 Windows 元数据库（.winmd 文件）时，ObsoleteAttribute 属性将导出为 ObsoleteAttribute 和 Windows.Foundation.DeprecatedAttribute。|  
|建议|使用 ObsoleteAttribute 属性的现有源代码的重新编译可能在从 C++/CX 或 JavaScript 使用该代码时生成警告。<br /><br /> 我们不建议将 ObsoleteAttribute 和 Windows.Foundation.DeprecatedAttribute 一起应用于托管程序集中的代码；这可能会导致生成警告。|  
|范围|边缘|  
|版本|4.5.1|  
|类型|重定目标|  
|分析器|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49：ResolveAssemblyReference 任务现在将对体系结构错误的依赖关系发出警告  
  
|||  
|-|-|  
|详细信息|此任务发出警告 MSB3270，它表示引用或任何依赖项不匹配应用程序的体系结构。 例如，如果使用 anycpu 选项编译的应用包括 x86 引用，则会发生此情况。 这样的情况可能导致运行时应用失败（在本例中为，如果应用部署为 x64 过程）。|  
|建议|有两方面的影响：<br /><br /> 重新编译将生成警告，当应用在以前版本的 MSBuild 下编译时，此类警告未显示。 但是，由于该警告可标识运行时失败可能的来源，所以应该调查并处理它。<br /><br /> 如果警告被视为错误，则应用将无法进行编译。|  
|范围|次要|  
|版本|4.5.1|  
|类型|重定目标|  
|分析器|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51：WPF 文本框默认撤消限制是 100  
  
|||  
|-|-|  
|详细信息|在 .NET 4.5 中，WPF 文本框的默认撤消限制是 100（.NET 4.0 则没有限制）|  
|建议|如果 100 的撤消限制过低，该限制可使用文本框的 UndoLimit 属性显式设置|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|分析器|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55：System.Threading.Tasks.Task 未观察处理中的异常不再在终接器线程上传播  
  
|||  
|-|-|  
|详细信息|由于 System.Threading.Tasks.Task 类表示异步操作，它捕获在异步处理过程中出现的所有非严重异常。 在 .NET Framework 4.5 中，如果未观察到异常，且代码绝不会等待任务，则异常将不再在终结器线程上传播并在垃圾回收期间不会导致进程崩溃。 此更改增强了使用 Task 类执行未观察到的异步处理的应用程序的可靠性。|  
|建议|如果应用依赖于未观察到的异步异常传播到终接器线程，可通过向 [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx) 事件提供相应的处理程序，或通过设置[运行时配置元素](https://msdn.microsoft.com/library/jj160346%28v=vs.110%29.aspx)来还原以前的行为。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|分析器|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58：IAsyncResult.CompletedSynchronously 属性必须正确，才能完成生成的任务  
  
|||  
|-|-|  
|详细信息|在调用 TaskFactory.FromAsync 时，必须正确实现 IAsyncResult.CompletedSynchronously 属性，才能完成生成的任务。 即，当且仅当同步完成实现时，该属性才应返回 true。 之前，属性未被选中。|  
|建议|如果仅在任务同步完成时，IAsyncResult 实现才为 CompletedSynchronusly 属性正确返回 true，将观察不到任何中断。 用户应查看所拥有的 IAsyncResult 实现（如果有），确保能够正确评估某项任务是否同步完成。|  
|范围|边缘|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 API|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName>|  
|分析器|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59：ObjectContext.CreateDatabase 方法创建的日志文件名已更改，以匹配 SQL Server 规范  
  
|||  
|-|-|  
|详细信息|当直接调用 CreateDatabase 方法或通过使用 Code First 与 SqlClient 提供程序以及连接字符串中的 AttachDBFilename 值来调用此方法时，它将创建一个名为 filename_log.ldf 而非 filename.ldf 的日志文件（其中 filename 是 AttachDBFilename 值指定的文件的名称）。 此更改通过提供根据 SQL Server 规范命名的日志文件来改进调试。|  
|建议|如果日志文件名对应用而言很重要，应更新该应用，以使用标准的 _log.ldf 文件名格式。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|分析器|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60：Page.LoadComplete 事件不再使 System.Web.UI.WebControls.EntityDataSource 控件调用数据绑定  
  
|||  
|-|-|  
|详细信息|`Page.LoadComplete` 事件不再导致 System.Web.UI.WebControls.EntityDataSource 控件针对 create/update/delete 参数的更改来调用数据绑定。 此更改消除到数据库的外来行程、防止重置控件的值，并生成与其他数据控件一致的行为，例如 SqlDataSource 和 ObjectDataSource。 在应用程序依赖于在 `Page.LoadComplete` 事件中调用数据绑定的极少数情况下，此更改会产生不同的行为。|  
|建议|如果需要数据绑定，请在回发之前的事件中手动调用数据绑定。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61：WebUtility.HtmlDecode 不再对无效的输入序列进行解码  
  
|||  
|-|-|  
|详细信息|默认情况下，解码方法不再将无效的输入序列解码为无效的 UTF-16 字符串。 相反，它们将返回原始的输入。|  
|建议|仅当你存储二进制数据而不是字符串中的 UTF-16 数据时，解码器输出中的更改才会起作用。 若要显式控制此行为，请将 [appSettings](https://msdn.microsoft.com/library/ms228154\(v=vs.110\).aspx) 元素的 `aspnet:AllowRelaxedUnicodeDecoding` 属性设置为 true 以支持旧行为，或设置为 false 以支持当前行为。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|分析器|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63：通过使用 SHA-256 代码签名证书的 ClickOnce 发布的应用在 Windows 2003 中可能会失败  
  
|||  
|-|-|  
|详细信息|使用 SHA256 对可执行文件签名。 以前，无论代码签名证书是 SHA-1 还是 SHA-256，都使用 SHA1 进行签名。 这适用于：<br /><br /> 使用 Visual Studio 2012 或更高版本生成的所有应用程序。<br /><br /> 使用 Visual Studio 2010 或更早版本在安装了 .NET Framework 4.5 的系统上生成的应用程序。<br /><br /> 此外，如果安装了 .NET Framework 4.5 或更高版本，则 ClickOnce 清单也会采用 SHA-256 签名，因为 SHA-256 证书与编译所采用的 .NET Framework 版本无关。|  
|建议|更改 ClickOnce 可执行文件的签名仅影响 Windows Server 2003 系统；它们需要安装 KB 938397。<br /><br /> 即使应用是面向 .NET Framework 4.0 或早期版本，对使用 SHA-256 签名的清单进行更改，将引入依赖 .NET Framework 4.5 或更高版本的运行时。|  
|范围|边缘|  
|版本|4.5-4.6|  
|类型|重定目标|  
|分析器|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68：DbParameter.Precision 和 DbParameter.Scale 现在是公共虚拟成员  
  
|||  
|-|-|  
|详细信息|DbParameter.Precision 和 DbParameter.Scale 已实现为公共虚拟属性。 它们替换相应的显式接口实现 DbParameter.IDbDataParameter.Precision 和 DbParameter.IDbDataParameter.Scale。|  
|建议|在重新生成 ADO.NET 数据库提供程序时，这些差异要求将“override”关键字应用到 Precision 和 Scale 属性。 仅在重新生成组件时才需要这样做；现有二进制文件将继续运行。|  
|范围|次要|  
|版本|4.5.1|  
|类型|重定目标|  
|受影响的 API|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|分析器|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73：DataObject.GetData 现在将数据检索为 UTF-8  
  
|||  
|-|-|  
|详细信息|对于面向 .NET Framework 4 或者在 .NET Framework 4.5.1 或早期版本上运行的应用，DataObject.GetData 将 HTML 格式的数据检索为 ASCII 字符串。 因此，非 ASCII 字符（ASCII 代码大于 0x7F 的字符）由两个随机字符表示。<br /><br /> 对于面向 .NET Framework 4.5 或更高版本以及在 .NET Framework 4.5.2 上运行的应用，`DataObject.GetData` 将 HTML 格式的数据检索为 UTF-8，从而可以正确表示大于 0x7F 的字符。|  
|建议|如果使用 HTML 格式的字符串实现了编码问题的解决方法（例如，通过将其传递到 UTF8Encoding.GetString 方法来显式编码从剪贴板检索的 HTML 字符串），而且要将应用的目标从版本 4 重定为 4.5，则应该删除该解决方法。<br /><br /> 如果出于某种原因需要使用以前的版本，该应用可面向 .NET Framework 4.0 来获取该行为。|  
|范围|边缘|  
|版本|4.5.2|  
|类型|重定目标|  
|受影响的 API|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|分析器|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75：默认应用域的 TargetFrameworkName 不再默认为 null（如果未设置）  
  
|||  
|-|-|  
|详细信息|以前，除非显式设置，否则默认应用域中的 TargetFrameworkName 为 null。 从 4.6 开始，默认应用域的 TargetFrameworkName 属性将具有派生自 TargetFrameworkAttribute 的默认值（如果存在）。 除非显式重写，否则非默认应用域将继续从默认应用域继承 TargetFrameworkName（在 4.6 中不会默认为 null）。|  
|建议|应更新代码，以独立于默认为 null 的 `AppDomainSetup.TargetFrameworkName`。 如果需要此属性继续评估为 null，它可显式设为该值。|  
|范围|边缘|  
|版本|4.6|  
|类型|运行时|  
|受影响的 API|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|分析器|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76：现在当 .NET 无法处理证书时，不会引发 X509Certificate2.ToString(bool)  
  
|||  
|-|-|  
|详细信息|以前如果为详细参数传递“true”，并且安装了 .Net Framework 不支持的证书，将引发此方法。 现在，该方法将取得成功，并返回省略证书无法访问部分的有效字符串。|  
|建议|应更新任何依赖 X509Certificate2.ToString(bool) 的代码，以希望返回的字符串会排除在某些情况下，API 之前曾引发的某些证书数据（例如公钥、私钥和扩展）。|  
|范围|边缘|  
|版本|4.6|  
|类型|运行时|  
|受影响的 API|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|分析器|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77：反射对象可能无法再从托管代码传递至进程外 DCOM 客户端  
  
|||  
|-|-|  
|详细信息|反射对象可能无法再从托管代码传道至进程外客户端 以下类型将受影响：<br /><br /> Assembly<br /><br /> MemberInfo（及其派生类型，包括 FieldInfo、MethodInfo、Type 和 TypeInfo）<br /><br /> MethodBody<br /><br /> 模块<br /><br /> ParameterInfo。<br /><br /> 调用对象的 `IMarshal` 会返回 `E_NOINTERFACE`。|  
|建议|更新封送代码，以与非反射对象一起使用|  
|范围|次要|  
|版本|4.6|  
|类型|运行时|  
|分析器|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78：ContentDisposition DateTimes 返回稍微不同的字符串  
  
|||  
|-|-|  
|详细信息|从 4.6 开始，已更新 ContentDispositions 的字符串表示形式，以始终使用两位数表示 DateTime 的小时部分。 这是为了符合 [RFC822](http://www.ietf.org/rfc/rfc0822.txt) 和 [RFC2822](http://www.ietf.org/rfc/rfc2822.txt)。 这将导致在 4.6 中，当其中一个处理时间元素早于上午 10 点时，`ContentDisposition.ToString` 将返回稍微不同的字符串。 请注意，ContentDispositions 有时通过将它们转换为字符串以进行序列化，因此应检查任何 ContentDisposition ToString 操作、序列化或 GetHashCode 调用。|  
|建议|不要期望不同 .NET Framework 版本的 ContentDispositions 的字符串表示形式相互进行正确比较。 如果可以，请在执行比较前将字符串转换回 ContentDispositions。|  
|范围|次要|  
|版本|4.6|  
|类型|运行时|  
|受影响的 API|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|分析器|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82：WorkflowDesigner.Load 不会删除符号属性  
  
|||  
|-|-|  
|详细信息|当在工作流设计器中面向 .NET Framework 4.5，并使用 WorkflowDesigner.Load() 方法加载重新托管的 3.5 工作流时，保存该工作流的同时将引发 XamlDuplicateMemberException。|  
|建议|此 bug 仅当在工作流设计器中面向 .NET Framework 4.5 时才显示，因此可通过将 `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName` 设为 4.0 .NET Framework 进行解决。<br /><br /> 或者，使用 [WorkflowContext.Load(string)](https://msdn.microsoft.com/library/ee425926\(v=vs.110\).aspx) 方法（而非 [WorkflowDesigner.Load()](https://msdn.microsoft.com/library/ee403482\(v=vs.110\).aspx)）加载该工作流可避免此问题出现。|  
|范围|主要|  
|版本|4.5-4.5.2|  
|类型|重定目标|  
|受影响的 API|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|分析器|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83：SqlConnection.Open 在存在非 IFS Winsock BSP 或 LSP 的 Windows 7 中会失败  
  
|||  
|-|-|  
|详细信息|如果在存在非 IFS Winsock BSP 或 LSP 的 Windows 7 计算机上运行，SqlConneciton.Open 和 OpenAsync 在 .NET Framework 4.5 中将会失败。<br /><br /> 若要确定是否安装了非 IFS BSP 或 LSP，请使用 `netsh WinSock Show Catalog` 命令，并查看每个返回的 `Winsock Catalog Provider Entry` 项。 如果服务标志值设置了 `0x20000` 位，提供程序将使用 IFS 句柄，并将正确运行。 如果 `0x20000` 位已清除（未设置），则它将是非 IFS BSP 或 LSP。|  
|建议|此 bug 已在 .NET Framework 4.5.2 中得到修复，因此升级 .NET Framework 可避免出现此问题。 或者，可通过删除任何已安装的非 IFS Winsock LSP 来避免出现此问题。|  
|范围|次要|  
|版本|4.5-4.5.2|  
|类型|运行时|  
|受影响的 API|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|分析器|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84：ICommand.CanExecuteChanged 事件行为已在 .NET 4.5 中更改  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.5 中，已忽略 CanExecuteChangedEvent，除非事件的发送程序与引发事件的对象是同一个对象。 此 bug 已在 .NET Framework 4.5 服务更新中修复。|  
|建议|此 bug 已在 .NET Framework 4.5 服务版本中修复，因此确保 .NET Framework 处于最新状态或升级到 .NET Framework 4.5.1 可避免此问题出现。 或者，可修改使用 ICommand 的应用程序代码，确保引发 CanExecuteChanged 命令的发送程序与引发该事件的对象是同一对象。|  
|范围|次要|  
|版本|4.5-4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|分析器|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85：一些 .NET API 会导致最可能的（已处理）EntryPointNotFoundExceptions  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.5 中，少量 .NET 方法开始引发最可能的 EntryPointNotFoundExceptions。 这些异常在 .NET Framework 内进行处理，但可能会中断不希望出现最可能的异常的测试自动化。 启用 HighVersionLie 后，这些相同的 API 会中断一些 ApiVerifier 方案。|  
|建议|升级到 .NET Framework 4.5.1 可避免此 bug 出现。 还可以更新测试自动化以便不中断对最可能的 EntryPointNotFoundExceptions 的操作。|  
|范围|边缘|  
|版本|4.5-4.5.1|  
|类型|运行时|  
|受影响的 API|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|分析器|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86：在 VirtualizingStackPanel 中滚动 WPF TreeView 或分组的 ListBox 可能导致暂停  
  
|||  
|-|-|  
|详细信息|在 .NET Framework v4.5 中，如果视区中存在边距（例如在 TreeView 的项目之间或在 ItemsPresenter 元素上），则在虚拟化堆叠面板中滚动 WPF TreeView 可能会导致暂停。 此外，在某些情况下，即使没有边距，视图中不同大小的项目也可能会导致不稳定性。|  
|建议|升级到 .NET Framework 4.5.1 可避免此 bug 出现。 或者，如果包含的所有项目大小相同，可从虚拟化堆叠面板的视图集合（例如 TreeView）中删除边距。|  
|范围|主要|  
|版本|4.5-4.5.1|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Controls.VirtualizingPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|分析器|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89：Type.IsAssignableFrom 会针对具有约束的泛型变量返回错误结果  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.5 中，Type.IsAssignableFrom 在所有情况下会针对具有约束的某些泛型类型错误地返回 `false`。|  
|建议|此问题已在服务更新中得到解决。 请更新 .NET Framework 4.5，或升级到 .NET Framework 4.5.1 或更高版本，以解决此问题。 或者，避免将 IsAssignableFrom 与对泛型参数拥有约束的泛型类型一起使用。 反射 API 可用作解决方法。|  
|范围|次要|  
|版本|4.5-4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|分析器|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91：EntityFramework 6.0 在从 Visual Studio 启动的应用中会非常缓慢地加载  
  
|||  
|-|-|  
|详细信息|从 Visual Studio 2013 启动使用 EntityFramework 6.0 的应用可能会非常缓慢。|  
|建议|此问题已在 EntityFramework 6.0.2 中解决。 请更新 EntityFramework 以避免此性能问题发生。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92：使用 AntiXSSEncoder 时，多行 ASP.Net 文本框间距已更改  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.0 中，如果使用 `AntiXSSEncoder`，则多余行将插入回发的多行文本框中的各行之间。 在 .NET Framework 4.5 中，不包括这些多余的换行符，仅在 Web 应用面向 .NET 4.5 时才可包含|  
|建议|请注意，面向 .NET 4.5 的 4.0 Web 应用可能改进了多行文本框，从而不再插入多余的换行符。 如果不需要这样做，当应用在 .NET Framework 4.5 上运行时，通过面向 .NET Framework 4.0 可使用旧行为。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|分析器|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95：ConcurrentQueue\<T>.TryPeek 可通过 Out 参数返回错误的 null  
  
|||  
|-|-|  
|详细信息|在某些多线程情况下，`ConcurentQueue<T>.TryPeek` 可返回 true，但使用 null 值填充 Out 参数（而非正确的扫视值）。|  
|建议|此问题已在 .NET Framework 4.5.1 中解决。 升级到该 Framework 即可解决该问题。|  
|范围|主要|  
|版本|4.5-4.5.1|  
|类型|运行时|  
|受影响的 API|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|分析器|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98：单个 TableLayoutPanel 单元格中的多个项目可能会重新排列  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.5 中，如果多个项目放置在同一 TableLayoutPanel 单元格中，它们的显示顺序可能会与 .NET Framework 4.0 中的顺序不同。|  
|建议|此行为已在 .NET Framework 4.5 的服务更新中还原。 请更新 .NET Framework 4.5，或升级到 .NET Framework 4.5.1 或更高版本，以解决此问题。 或者，避免在同一 TableLayourPanel 单元格中出现多个项目的不明情况。|  
|范围|次要|  
|版本|4.5-4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|分析器|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100：Foreach 迭代器变量现在已在迭代范围内，因此闭包捕获语义会不同（在 C#5 中）  
  
|||  
|-|-|  
|详细信息|从 C# 5 (Visual Studio 2012) 开始，foreach 迭代器变量在迭代范围内。 如果代码以前依靠变量而不在 foreach 闭包内，这可能会导致中断。 此更改的特征如下：传递到委托的迭代器变量将视为委托创建时它拥有的值，而非调用委托时它拥有的值。|  
|建议|理想情况下，应更新代码以使用新的编译器行为。 如果需要旧语义，迭代器变量可替换为显式置于循环范围外的单独变量。|  
|范围|主要|  
|版本|4.5|  
|类型|重定目标|  
|分析器|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101：HtmlTextWriter 未正确呈现 \`<br/\>` 元素  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.6 开始，调用带有 `<BR />` 的 `HtmlTextWriter.RenderBeginTag()` 和 `HtmlTextWriter.RenderEndTag()` 将正确插入唯一 `<BR />`（而非两个）|  
|建议|如果应用依赖于多余的 `<BR />` 标记，应再次调用 `HtmlTextWriter.RenderBeginTag()`。 请注意，此行为更改仅影响面向 .NET Framework 4.6 的应用，因此另一选项是面向以前版本的 .NET Framework 以便获取旧行为。|  
|范围|边缘|  
|版本|4.6|  
|类型|重定目标|  
|受影响的 API|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|分析器|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104：在选定项目的 WPF ListBox、ListView 或 DataGridCalling 上调用 Items.Refresh 可能会导致元素中出现重复项目  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.5 中，在项目已在 ListBox 中选定的同时从代码中调用 ListBox.Items.Refresh 可能会导致选定项目在列表中重复。 ListView 和 DataGrid 会出现类似问题。 此问题已在 .NET Framework 4.6 中解决。|  
|建议|在调用 Refresh 前以编程方式取消选择项目，然后在调用完成后重新选择它们，可解决该问题。 此外，此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。|  
|范围|次要|  
|版本|4.5-4.6|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|分析器|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105：ETW EventListeners 无法从具有显式关键字的提供程序中（例如 TPL 提供程序）捕获事件  
  
|||  
|-|-|  
|详细信息|具有空白关键字掩码的 ETW EventListeners 无法从具有显式关键字的提供程序中正确捕获事件。 在 .NET Framework 4.5 中，TPL 提供程序开始提供显式关键字，引发了此问题。 在 .NET Framework 4.6 中，EventListeners 已更新，此问题不再存在。|  
|建议|若要解决此问题，则将对 EnableEvents(eventSource, level) 的调用替换为 EnableEvents 重载，以显式指定要使用的“任意关键字”掩码：`EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`。<br /><br /> 此外，此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。|  
|范围|边缘|  
|版本|4.5-4.6|  
|类型|运行时|  
|受影响的 API|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|分析器|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109：如果使用 EntityDeploySplit 或 EntityClean 任务，使用 Visual Studio 2013 生成实体框架 edmx 会失败，错误编码为 MSB4062  
  
|||  
|-|-|  
|详细信息|MSBuild 12.0 工具（包括在 Visual Studio 2013 中）更改了 msbuild 文件位置，使得旧实体框架目标文件变为无效文件。 结果是 `EntityDeploySplit` 和 `EntityClean` 任务失败，因为它们无法找到 `Microsoft.Data.Entity.Build.Tasks.dll`。 请注意，此中断是由于工具集 (msbuild/VS) 更改而引起的，并不是因为 .NET Framework 更改。 它仅在升级开发人员工具时才会发生，仅升级 .NET Framework 不会发生。|  
|建议|从 .NET Framework 4.6 开始，实体框架目标文件已修复，可与新 msbuild 布局一起使用。 升级到该版本的 Framework 将解决此问题。 或者，可使用[此](http://stackoverflow.com/a/24249247/131944)解决方法直接修补目标文件。|  
|范围|主要|  
|版本|4.5.1-4.6|  
|类型|重定目标|  
|分析器|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111：如果使用复合密钥并且一个密钥为空，XSD 架构验证现在可正确检测是否违反唯一约束  
  
|||  
|-|-|  
|详细信息|在版本 4.6 之前的 .NET Framework 版本中存在一个 bug，即如果其中一个密钥为空，XSD 验证无法检测复合密钥上的唯一约束。 在 .NET Framework 4.6 中，此问题已得到更正。 这将导致更多的正确验证，但也可能导致无法像以前版本那样验证某些 XML。|  
|建议|如果放宽要求，需要 .NET Framework 4.0 验证，该验证应用程序可以面向版本 4.5（或更早版本）的 .NET Framework。 但在重定目标至 .NET 4.6 时，应执行代码评审以确定重复的复合密钥（如在此问题的描述中所述）无需验证。|  
|范围|边缘|  
|版本|4.6|  
|类型|重定目标|  
|分析器|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112：如果多义性可按索引类型进行解析，则在索引器属性上调用 Attribute.GetCustomAttributes 将不再引发 AmbiguousMatchException  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.6 之前的版本中，在仅按索引类型划分区别的索引器属性上调用 `GetCustomAttribute(s)` 将引发 `AmbiguousMatchException`。 从 .NET Framework 4.6 开始，将正确返回该属性的属性。|  
|建议|请注意，GetCustomAttribute 现在将更频繁地运行。 如果应用以前依赖于 `AmbiguousMatchException`，现在应改用反射以显式查找多个索引器。|  
|范围|边缘|  
|版本|4.6|  
|类型|运行时|  
|受影响的 API|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|分析器|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113：使用自定义 DataTemplates 时，在 ItemsControls（例如 ListBox 和 DataGrid）内间歇性无法滚动到底部项目  
  
|||  
|-|-|  
|详细信息|在某些情况下，使用自定义 DataTemplates 时，.NET Framework 4.5 中的 bug 引起 ItemsControls（例如 ListBox、ComboBox、DataGrid 等）无法滚动到底部项目。 如果再次尝试滚动（在可重新滚动后），将可以滚动。|  
|建议|此问题已在 .NET Framework 4.5.2 中解决，升级到该版本（或更高版本）的 .NET Framework 即可解决该问题。 或者，用户仍可将滚动条拖动至这些集合中的最后几个项目，但可能需要尝试两次才能成功。|  
|范围|次要|  
|版本|4.5-4.5.2|  
|类型|运行时|  
|分析器|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114：从 .NET 4.5 开始，GlyphRun.ComputeInkBoundingBox() 和 FormattedText.Extent 返回不同的值  
  
|||  
|-|-|  
|详细信息|.NET Framework 4.5 改进了 GlyphRun.ComputeInkBoundingBox() 和 FormattedText.Extent，以解决在 .NET Framework 4.0 中，框在某些情况下因过小而无法包含字形的问题。 因此，从 .NET Framework 4.5 开始，某些范围框将更大，从而使 UI 布局产生细微差异。|  
|建议|请注意，某些字形范围框大小已增加。 这些更改通常会改进展示和点击框测试，但如果需要使用旧（.NET 4.5 之前的）行为，可通过以下条目添加到 app.config 文件进行选择：<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|分析器|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124：从 CellEditEnding 处理程序调用 DataGrid.CommitEdit 将丢失焦点  
  
|||  
|-|-|  
|详细信息|从某个 DataGrid 的 CellEditEnding 事件处理程序调用 DataGrid.CommitEdit 将导致 DataGrid 丢失焦点。|  
|建议|此 bug 已在 .NET Framework 4.5.2 中得到修复，因此升级 .NET Framework 可避免出现此问题。 或者，可通过在调用 CommitEdit 后显式重新选择 DataGrid 避免出现此问题。|  
|范围|边缘|  
|版本|4.5-4.5.2|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|分析器|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125：ASP.NET MVC 现在将转义通过路由参数传递的字符串中的空格  
  
|||  
|-|-|  
|详细信息|为了遵守 RFC 2396，从路由中填充操作参数时，现在将转义路由路径中的空格。 因此，尽管 `/controller/action/some data` 之前会匹配路由 `/controller/action/{data}` 并提供 `some data` 作为数据参数，但它现在将改为提供 `some%20data`。|  
|建议|应更新代码，以取消转义路由中的字符串参数。 如果需要原始 URI，可通过 Request.RequestUri.OriginalString API 进行访问。|  
|范围|次要|  
|版本|4.5.2|  
|类型|运行时|  
|受影响的 API|[System.Web.Http.RouteAttribute](https://msdn.microsoft.com/library/system.web.http.routeattribute(v=vs.118).aspx)|  
|分析器|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127：VB.NET 不再支持 System.Windows API 的部分命名空间限定  
  
|||  
|-|-|  
|详细信息|从 .NET 4.5.2 开始，VB.NET 项目无法通过部分限定命名空间指定 System.Windows API。 例如，对 `Windows.Forms.DialogResult` 的引用将失败。 而代码必须引用完全限定名称 (`System.Windows.Forms.DialogResult`)，或导入特定命名空间并仅引用 `DialogResult`。|  
|建议|应更新代码，以使用简单名称（并导入相关命名空间）或使用完全限定名称来引用 `System.Windows` API。|  
|范围|次要|  
|版本|4.5.2|  
|类型|重定目标|  
|分析器|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129：不支持对具有非公共资源库的属性的双向数据绑定  
  
|||  
|-|-|  
|详细信息|尝试将数据绑定到没有公共资源库的方案从未受支持。 从 .NET Framework 4.5.1 开始，此方案将引发 InvalidOperationException。 请注意，仅专门面向 .NET Framework 4.5.1 的应用会引发此新异常。 如果应用面向 .NET Framework 4.5，将允许该调用。 如果应用不面向特定 .NET Framework 版本，绑定将视为单向绑定。|  
|建议|应更新应用以使用单向绑定，或公开公布属性的资源库。 或者，面向 .NET Framework 4.5 将使应用展示旧行为。|  
|范围|次要|  
|版本|4.5.1|  
|类型|重定目标|  
|受影响的 API|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|分析器|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130：Marshal.SizeOf 和 Marshal.PtrToStructure 重载中断动态代码  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.5.1 开始，动态绑定到方法 `Marshal.SizeOf` 或 `Marshal.PtrToStructure`（例如通过 Windows PowerShell、IronPython 或 C# dynamic 关键字）将引发 `MethodInvocationExceptions`，因为这些方法的新重载已添加，使得对于脚本引擎而言可能不明确。|  
|建议|更新脚本以清楚指示应使用哪个重载。 通常，这可通过将方法的类型参数显式转换为 `System.Type` 来实现。 有关如何解决此问题的详细信息和示例，请参阅[此链接](https://support.microsoft.com/kb/2909958/)。|  
|范围|次要|  
|版本|4.5.1|  
|类型|运行时|  
|分析器|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131：如果 PreviewLostKeyboardFocus 的处理程序显示 Windows 窗体消息框，将重复调用它  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.5 开始，在消息框关闭时，从 `UIElement.PreviewLostKeyboardFocus` 处理程序中调用 `System.Windows.Forms.MessageBox.Show` 将重新触发该处理程序，从而可能会导致消息框无限循环出现。|  
|建议|有两种选项可以解决此问题：<br /><br /> 调用 `System.Windows.MessageBox.Show`（而非 `System.Windows.Forms.MessageBox.Show`）可避免此问题出现。<br /><br /> 在 `LostKeyboardFocus` 事件处理程序中显示消息框可避免此问题出现（这与 `PreviewLostKeyboardFocus` 事件处理程序的情况不同）。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 API|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|分析器|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133：在 .NET 4.5 中使用 NetDataContractSerializer 序列化的 ConcurrentDictionary 无法通过 .NET 4.5.1 或 4.5.2 反序列化  
  
|||  
|-|-|  
|详细信息|由于对类型作了内部更改，因此在 .NET Framework 4.5 中使用 `NetDataContractSerializer` 序列化的 `System.Collections.Concurrent.ConcurrentDictionary` 对象无法在 .NET Framework 4.5.1 或 .NET Framework 4.5.2 中反序列化。<br /><br /> 请注意，反向操作（在 .NET Framework 4.5.x 中序列化，而在 .NET Framework 4.5 中反序列化）将奏效。 同样，所有 4.x 跨版本序列化均与 .NET Framework 4.6 兼容。<br /><br /> 单个版本的 .NET Framework 的序列化和反序列化不受影响。|  
|建议|如果需要在 .NET Framework 4.5 和 .NET Framework 4.5.1/4.5.2 之间序列化和反序列化 ConcurrentDictionary，应使用 DataContractSerializer 或 BinaryFormatter 序列化程序之类的备用序列化程序，而非使用 NetDataContractSerializer。<br /><br /> 或者，由于此问题已在 .NET Framework 4.6 中解决，因此升级件到该版本的 .NET Framework 即可解决该问题。|  
|范围|次要|  
|版本|4.5.1-4.6|  
|类型|运行时|  
|分析器|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134：波斯日历现在使用回历太阳能算法  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.6 开始，PersianCalendar 类使用回历太阳能算法。 从 .NET Framework 4.6 开始，对于早于 1800 年或晚于 2023 年（公历）的日期，在 PersianCalendar 和其他日历之间转换日期所得结果可能略微不同。<br /><br /> 另外，`PersianCalendar.MinSupportedDateTime` 现在是 `March 22, 0622 instead of March 21, 0622`。|  
|建议|请注意，在 .NET 4.6 中使用 PersianCalendar 时，某些较早或较晚的日期可能略微不同。 另外，当在不同 .NET Framework 版本上运行的进程之间序列化日期时，请勿将它们存储为 PersianCalendar 日期字符串（因为这些值可能不相同）。|  
|范围|次要|  
|版本|4.6|  
|类型|运行时|  
|受影响的 API|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|分析器|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138：调用具有 null 自变量的 CreateDefaultAuthorizationContext 的方式已更改  
  
|||  
|-|-|  
|详细信息|调用具有 null authorizationPolicies 自变量的 `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)` 所返回的 AuthorizationContext 实现更改了其在 .NET Framework 4.6 中的实现。|  
|建议|在极少数情况下，使用自定义身份验证的 WCF 应用可能会看到行为差异。 在这类情况下，可使用以下两种方式之一还原以前的行为：<br /><br /> 重新编译你的应用以面向早于 4.6 的 .NET Framework 版本。 对于 IIS 承载的服务，请使用 \<httpRuntime targetFramework="x.x" /> 元素以面向早期版本的 .NET Framework。<br /><br /> 将下面的行添加到 app.config 文件的 `<appSettings>` 部分：`<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`|  
|范围|次要|  
|版本|4.6|  
|类型|重定目标|  
|受影响的 API|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|分析器|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141：WPF TreeViewItem 必须在 TreeView 内使用  
  
|||  
|-|-|  
|详细信息|4.5 中引入了一项更改，即限制在 TreeView 外使用 TreeViewItem。 在下列条件下，可能会出现这种情况：<br /><br /> TreeViewItem 的视觉父级并非是一个面板。 （为 TreeView 生成的 TreeViewItem 将有一个面板作为其父级）<br /><br /> TreeViewItem 是充当列表控件（ListBox、DataGrid、ListView 等）“项目主机”的 VirtualizingStackPanel 的后代。 无需启用虚拟化。<br /><br /> VirtualizingStackPanel 可以滚动项目 (`ScrollUnit="Item"`)。<br /><br /> 有些用户调用 `VirtualizingStackPanel.MakeVisible(v)` 以将元素 `v` 滚动至视图。 这可通过许多方法显式或隐式实现；或许最常见的方法是，只需单击 `v` 即可为其提供键盘焦点。<br /><br /> 视觉父链贯穿整个 TreeViewItem，范围从 `v` 到 VirtualizingStackPanel。<br /><br /> 换言之，在 TreeView 之外使用 TreeViewItem，并且用户单击 TreeViewItem 的某个后代以显示它后，便可显示。 如果 TreeViewItem 的后代都没有焦点，将永远不会遇到此问题。 例如，如果 TreeViewItem 是 DataTemplate 的根，则会出现此问题。  发生此问题时，WPF 框架中将引发 InvalidCastException。|  
|建议|将向此问题提供修补程序。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143：X509CertificateClaimSet.FindClaims 考虑到所有 claimTypes  
  
|||  
|-|-|  
|详细信息|在面向 .NET Framework 4.6.1 的应用中，如果 X509 声明集从 SAN 字段拥有多个 DNS 条目的证书初始化，FindClaims 方法会尝试将 claimType 自变量与所有 DNS 条目进行匹配。<br /><br /> 对于面向 .NET Framework 先前版本的应用，FindClaims 方法尝试仅将 claimType 自变量与最后一个 DNS 条目进行匹配。|  
|建议|此更改仅影响面向 .NET Framework 4.6.1 的应用程序。 在 [DisableMultipleDNSEntries](https://msdn.microsoft.com/library/mt620030%28v=vs.110%29.aspx) 兼容性开关中，可能会禁用此更改（如果面向 4.6.1 之前的版本，将启用此更改）。|  
|范围|次要|  
|版本|4.6.1|  
|类型|重定目标|  
|受影响的 API|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|分析器|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144：IMessageFilter.PreFilterMessage 的可重入实现不会再引发 Application.FilterMessage  
  
|||  
|-|-|  
|详细信息|在 .NET Framework 4.6.1 之前的版本中，调用 Application.FilterMessage 和 IMessageFilter.PreFilterMessage（这已调用 AddMessageFilter 或 RemoveMessageFilter，同时也调用 Application.DoEvents）将会引发 IndexOutOfRangeException。<br /><br /> 从面向 .NET Framework 4.6.1 的应用程序开始，不再引发此异常，并且可能使用上述的可重入筛选器。|  
|建议|请注意，上述的可重入 IMessageFilter.PreFilterMessage 行为将不会再引发 Application.FilterMessage。 此更改仅影响面向 .NET Framework 4.6.1 的应用程序。<br /><br /> 面向 .NET Framework 4.6.1 的应用可使用 [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/library/mt620032%28v=vs.110%29.aspx) 兼容性开关，选择退出此更改（或者面向较早的 Framework 的应用可选择使用此更改）。|  
|范围|边缘|  
|版本|4.6.1|  
|类型|重定目标|  
|受影响的 API|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|分析器|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145：在 WPF 调度程序操作上不保留 CurrentCulture  
  
|||  
|-|-|  
|详细信息|从 .NET Framework 4.6 开始，在[调度程序](https://msdn.microsoft.com/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx)中对 CurrentCulture 或 CurrentUICulture 所做的更改将在调度程序操作末尾丢失。 同样，在调度程序操作外对 CurrentCulture 或 CurrentUICulture 所做的更改在执行该操作时可能不会反映出来。<br /><br /> 实际上，这意味着 CurrentCulture 和 CurrentUICulture 更改可能不会在 WPF UI 回叫和 WPF 应用程序中的其他代码之间流动。<br /><br /> 这是因为，从面向 .NET Framework 4.6 的应用开始，[ExecutionContext](https://msdn.microsoft.com/library/system.threading.executioncontext%28v=vs.110%29.aspx) 中的一项更改使 CurrentCulture 和 CurrentUICulture 存储在执行上下文中。 WPF 调度程序操作存储用于启动操作的执行上下文，并在操作完成时还原以前的上下文。 由于 CurrentCulture 和 CurrentUICulture 现在属于该上下文，因此在调度程序操作中对它们所做的更改在操作之外不会保留。|  
|建议|受此更改影响的应用可在字段中存储所需的 CurrentCulture 或 CurrentUICulture，并在所有调度程序操作正文（包括 UI 事件回叫处理程序）中检查是否设置了正确的 CurrentCulture 和 CurrentUICulture。 或者，因为在此 WPF 更改之下的 ExecutionContext 更改仅影响面向 .NET Framework 4.6 或更高版本的应用，面向 .NET Framework 4.5.2 可避免出现此中断。|  
|范围|次要|  
|版本|4.6|  
|类型|重定目标|  
|分析器|CD0145|
