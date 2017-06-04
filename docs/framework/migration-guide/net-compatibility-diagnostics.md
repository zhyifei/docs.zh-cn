---
title: ".NET 兼容性诊断 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: "twsouthwick"
ms.author: "tasou"
manager: "wpickett"
caps.handback.revision: 7
---
# .NET 兼容性诊断
.NET 兼容性诊断是功耗 Roslyn 分析器可帮助标识应用的.NET Framework 版本之间的兼容性问题。 此列表包含所有可用，分析器尽管只有一个子集将应用于任何特定的迁移。 分析器将确定哪些问题适用于计划的迁移，并仅将呈现这些。 有关的问题划分受影响的版本，请参阅︰[应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility.md)。  
  
 每个问题包括以下信息︰  
  
-   从以前的版本已更改内容的说明。  
  
-   的建议是更改如何影响客户和是否可用于跨版本保持兼容性问题的变通方法的说明。  
  
-   重要程度的更改是评估。 应用程序兼容性问题进行分类，如下所示︰  
  
    |||  
    |-|-|  
    |主要|显著的更改，可影响大量应用或需要修改大量代码。|  
    |次要|更改影响少量应用或需要修改少量代码。|  
    |边缘情况|仅影响应用程序非常具体，不常见的情况下的更改。|  
    |透明|更改与应用程序的开发人员或用户没有明显影响。|  
  
-   版本指示当更改首先出现在框架中。 某些所做的更改将会恢复，同时，也指示。  
  
-   更改的类型︰  
  
    |||  
    |-|-|  
    |重定目标|此更改影响那些编译为面向.NET Framework 的新版本的应用。|  
    |运行时|此更改影响面向以前版本的.NET framework 但在更高版本上运行现有应用程序。|  
  
-   受影响的 API 中，如果有的话。  
  
-   可用的诊断程序的 Id  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: SoapFormatter 无法反序列化哈希表和类似有序集合对象  
  
|||  
|-|-|  
|详细信息|SoapFormatter 不保证对象进行序列化版本将成功反序列化的其他版本下的下一个.NET Framework。 具体而言，某些有序的集合 （如哈希表） 增加了 4.0 和 4.5 之间的成员，以便这些类型的对象不能使用反序列化.NET 4.0 就像.NET 4.5 起 serialzied。 请注意，是否序列化的数据是序列化和反序列化使用相同的.NET Framework 版本，会出现任何问题。|  
|建议|应使用 BinaryFormatter 序列化或 NetDataContractSerialization 为能够弹性应对.NET Framework 更改替换 SoapFormatter 序列化。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> [SoapFormatter.Serialize (流中，对象，标头\<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|分析器|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: WPF DataTemplate 元素现在是 UIA 对可见  
  
|||  
|-|-|  
|详细信息|以前，DataTemplate 元素是 UI 自动化对不可见。 从开始在 4.5 中，UI 自动化将检测这些元素。 这是在许多情况下很有用，但可能会破坏依赖于不包含 DataTemplate 元素 UIA 树的测试。|  
|建议|UI Auomation 测试此应用程序可能需要更新，以考虑现在包括以前不可见的 DataTemplate 元素的 UIA 树结构。 例如，预计要彼此相邻的某些元素的测试现在可能需要期望以前不可见的 UIA 元素之间。 或使用新值更新为 UIA 元素可能需要依赖于基于特定的计数或索引的测试。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|分析器|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: WPF 文本框选择文本文本框中处于非活动状态时，将出现另一种颜色  
  
|||  
|-|-|  
|详细信息|在.NET 4.5 中，当 WPF 文本框控件处于非活动状态时 （不具有焦点），在框中所选的文本将显示该控件处于活动状态时不同的颜色。|  
|建议|可以通过设置还原之前的 (.NET 4.0) 行为[FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/en-us/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx)属性设置为 false。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|分析器|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: List<>\>.ForEach 可能会修改列表项时引发异常  
  
|||  
|-|-|  
|详细信息|从.NET 4.5 开始`List<T>.ForEach`枚举器将引发 InvalidOperationException 异常，如果修改调用集合中的元素。 以前，这将不会引发异常，但可能导致争用条件。|  
|建议|理想情况下，应修复代码，可以不在枚举及其元素，因为它永远不会是一项安全操作时修改的列表。 若要还原到以前的行为，不过，应用程序可能以目标.NET 4.0。|  
|范围|边缘|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|分析器|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: System.Uri 分析符合 RFC 3987  
  
|||  
|-|-|  
|详细信息|在.NET 4.5 中的几种方法，分析 URI 已更改。 但是请注意，这些更改仅影响面向.NET 4.5 代码。 如果二进制针对.NET 4.0，则将遵守这一旧行为。 对在.NET 4.5 中分析 URI 的更改包括︰<br /><br /> URI 分析将执行规范化和字符检查根据 RFC 3987 中的最新 IRI 规则<br /><br /> 只能将对 URI 的主机部分执行 Unicode 范式 C<br /><br /> 无效的 mailto: Uri 将立即导致引发异常<br /><br /> 现在保留路径段的末尾的尾随点<br /><br /> `file://`将不会转义 Uri`?`字符<br /><br /> Unicode 控制字符`U+0080`通过`U+009F`不受支持<br /><br /> 逗号字符`,`或`%2c`不会自动取消转义|  
|建议|如果旧的.NET 4.0 URI 解析语义必要 （通常它们），它们可通过针对.NET 4.0。 这可以通过使用 TargetFrameworkAttribute 针对程序集，或通过项目属性页中的 Visual Studio 项目系统用户界面。|  
|范围|主要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|分析器|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: System.Uri 转义现在支持 RFC 3986 (http://tools.ietf.org/html/rfc3986)  
  
|||  
|-|-|  
|详细信息|URI 转义以支持的.NET 4.5 中已更改[RFC 3986](http://tools.ietf.org/html/rfc3986)。 特定的更改包括︰<br /><br /> `EscapeDataString` 根据 RFC 3986 转义保留字符。<br /><br /> `EscapeUriString` 未转义保留字符。<br /><br /> 如果 `UnescapeDataString` 遇到无效的转义序列，则它不会引发异常。<br /><br /> 未保留的转义字符已取消转义。|  
|建议|更新应用程序不依赖于 UnescapeDataString 在无效的转义序列的情况下引发。 此类序列必须检测到直接现在。<br /><br /> 同样，期望 Escaped 和未转义 URI 以及数据的字符串可能在.NET 4.0 和.NET 4.5 之间变化，并应不会比较.NET 版本之间直接。 相反，它们应该分析并进行任何比较之前在单个的.NET 版本进行规范化。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|分析器|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11︰ 在 Windows 8 上不可用 system.net.peertopeer.collaboration 环境  
  
|||  
|-|-|  
|详细信息|在 Windows 8 或更高版本，则 system.net.peertopeer.collaboration 命名空间不可用。|  
|建议|应用程序支持 Windows 8 或更高版本必须更新以不依赖于此命名空间或它的成员。|  
|范围|主要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|分析器|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: MEF 目录实现 IEnumerable，因此可以不再可用于创建序列化程序  
  
|||  
|-|-|  
|详细信息|从.NET Framework 4.5 开始，MEF 目录实现 IEnumerable，因此可以不能再用于创建序列化程序 （XmlSerializer 对象）。 尝试对 MEF 目录进行序列化会引发异常。|  
|建议|不能再使用 MEF 来创建一个序列化程序|  
|范围|主要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13︰ 缺少目标框架名字对象会导致 4.0 行为  
  
|||  
|-|-|  
|详细信息|应用程序而无需[TargetFrameworkAttribute](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx)应用于程序集级别将会自动运行使用.NET Framework 4.0 的语义 (quirks)。 若要确保高质量，建议所有二进制文件显式将具有与同时生成 TargetFrameworkAttribute 表示.NET Framework 的版本。 请注意，在项目文件中使用的目标框架名字对象将 caues MSBuild 将自动应用 TargetFrameworkAttribute。|  
|建议|一个[目标框架特性](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx)应提供，则可以通过将属性添加对程序集直接或通过指定目标 framework[项目文件或通过 Visual Studio 项目属性 GUI](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx)。|  
|范围|主要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14︰ 不再能够将 EnableViewStateMac 设置为 false  
  
|||  
|-|-|  
|详细信息|ASP.NET 不再允许开发人员能够指定`<pages enableViewStateMac="false"/>`或`<@Page EnableViewStateMac="false" %>`。 现在，针对所有带嵌入视图状态的请求强制执行视图状态消息身份验证代码 (MAC)。 显式将 EnableViewStateMac 属性设置为 false 的唯一应用程序会受到影响。|  
|建议|EnableViewStateMac 必须被认为是真的，并且必须纠正任何生成的 MAC 错误 (如中所述[这](https://support.microsoft.com/en-us/kb/2915218)指南，其中包含多个解决方法，具体取决于什么原因导致 MAC 错误)。|  
|范围|主要|  
|版本|4.5.2|  
|类型|运行时|  
|分析器|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection<>\>。不会再引发 TryTakeFromAny  
  
|||  
|-|-|  
|详细信息|如果其中一个输入集合被标记为已完成，`BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)`不再返回-1 和`BlockingCollection<T>.TakeFromAny`不再引发异常。 当其中一个集合为空或已完成，但其他集合仍具有可检索的项时，可通过此更改来使用这些集合。|  
|建议|如果 TryTakeFromAny 返回-1 或 TakeFromAny 引发了控制流用途的阻碍性回收 θ ч 的情况下，此类代码现在应改为使用`.Any(b => b.IsCompleted)`来检测该条件。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|[BlockingCollection<>\>。TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>。TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>。TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>。TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>。TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|分析器|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: XmlSchemaException 现在集正确行位置  
  
|||  
|-|-|  
|详细信息|如果 LoadOptions.SetLineInfo 值传递到 Load 方法，会发生验证错误的 XmlSchemaException.LineNumber 和 XmlSchemaException.LinePosition 属性现在包含行信息。|  
|建议|假设 XmlSchemaException.LineNumber 和 XmlSchemaException.LinePosition 异常处理代码不会因为加载 XML 时使用 SetLineInfo 时，这些属性将立即正确设置应更新集。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|分析器|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities 现 APTCA  
  
|||  
|-|-|  
|详细信息|使用 AllowPartiallyTrustedCallersAttribute 特性进行标记程序集。|  
|建议|派生的类不能将用 SecurityCriticalAttribute 标记。 以前，派生的类型必须用 SecurityCriticalAttribute 标记。 但是，此更改不应有实际影响。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21︰ 工作流 3.0 类型已过时  
  
|||  
|-|-|  
|详细信息|Windows Workflow Foundation (WWF) 3.0 Api （System.Workflow 命名空间中的那些） 现已过时。|  
|建议|应改为使用新的 WWF 4.0 Api （在 System.Activities)。 找不到举例说明如何使用新的 Api[此处](https://msdn.microsoft.com/en-us/library/jj205427.aspx)和进一步提供了指导[此处](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx)。 此外，由于 WWF 3.0 Api 仍受支持，可能会使用它们，构建时警告避免通过禁止显示它，或使用较旧的编译器。|  
|范围|主要|  
|版本|4.5|  
|类型|重定目标|  
|分析器|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22︰ 某些工作流拖放式 Api 已过时  
  
|||  
|-|-|  
|详细信息|此工作流拖放 API 已废弃不用，针对 4.5 重新生成应用程序时，将导致编译器警告。|  
|建议|新[DragDropHelper](https://msdn.microsoft.com/en-us/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx)应改为使用支持多个对象的操作的 Api。 或者，可以禁止显示生成警告，或通过使用较旧的编译器可避免它们。 Api 仍受支持。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|分析器|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23︰ 新的 （不明确） Dispatcher.Invoke 重载可能导致不同的行为  
  
|||  
|-|-|  
|详细信息|.NET Framework 4.5 中的新重载添加 Dispatcher.Invoke 包括 System.Action 类型的参数。 当重新编译现有代码时，编译器可能会解决对 Dispatcher.Invoke 方法作为对 Dispatcher.Invoke 方法使用 System.Action 参数的调用具有一个委托参数的调用。 如果对与委托参数的 Dispatcher.Invoke 重载的调用被解析为对使用 System.Action 参数的 Dispatcher.Invoke 重载的调用，可能会出现以下行为差异︰<br /><br /> 如果发生异常，不会引发 Dispatcher.UnhandledExceptionFilter 和 Dispatcher.UnhandledException 事件。 相反，由 UnobservedTaskException 事件处理异常。<br /><br /> 对某些成员，如 DispatcherOperation.Result，调用阻止，直到操作完成。|  
|建议|若要避免多义性 （和异常处理或阻止行为的潜在差异），调用 Dispatcher.Invoke o d e 可以传递一个空的 object [] 作为第二个参数到解析为.NET 4.0 方法重载的以确保该 Invoke 调用。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 Api|[Dispatcher.Invoke (委托，对象\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (委托，TimeSpan 对象\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (委托、 DispatcherPriority，TimeSpan 对象\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (委托，DispatcherPriority，对象\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|分析器|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: EncoderParameter ctor 已过时  
  
|||  
|-|-|  
|详细信息|`EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)`构造函数现已过时，因此如果使用将介绍生成警告。|  
|建议|尽管`EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)`构造函数将继续正常工作，应改为使用下面的构造函数以重新编译使用.NET 4.5 工具的代码时避免过时生成警告︰ [EncoderParameter.EncoderParameter （编码器、 Int32、 EncoderParameterValueType、 IntPtr）](https://msdn.microsoft.com/en-us/library/hh875096\(v=vs.110\).aspx)。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|分析器|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: Task.WaitAll 带超时参数的方法的行为更改  
  
|||  
|-|-|  
|详细信息|在.NET 4.5，Task.WaitAll 行为进行更一致。<br /><br /> 在.NET Framework 4 中，这些方法的行为不一致。 当超时到期时，如果一个或多个任务已完成或已取消在方法调用之前时，该方法会引发 AggregateException 异常。 当超时到期时，如果任何任务已完成或已取消之前方法调用中，但一个或多个任务进入了这些状态，在方法调用后时，该方法返回 false。<br />在.NET Framework 4.5 中，这些方法重载现在如果返回 false 的任何任务仍在运行时的超时间隔过期，并将它们引发 AggregateException 异常，仅当某个输入的任务已取消 （无论它是在方法调用前后） 且没有其他任务仍在运行。|  
|建议|如果在 AggregateException 捕获作为一种检测已取消之前被调用的 WaitAll 调用代码应改为做通过作为 IsCanceled 属性的同一个检测任务 (例如:。任何 (t => t.IsCanceled)) 因为.NET 4.6 将只引发这种情况下，如果处于等待状态的所有任务都完成之前超时时间。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|[Task.WaitAll (任务\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [Task.WaitAll (任务\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [Task.WaitAll (任务\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|分析器|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27︰ 行为中的数据定义语言 (DDL) Api 中的行为更改  
  
|||  
|-|-|  
|详细信息|如果指定 AttachDBFilename DDL Api 的行为已更改，如下所示︰<br /><br /> 连接字符串不需要指定初始目录值。 以前，AttatchDBFilename 和初始目录是必需的。<br /><br /> 如果指定了 AttatchDBFilename 和初始目录，并且给定的 MDF 文件存在，则该 ObjectContext.DatabaseExists 方法返回 true。 以前，它会返回 false。<br /><br /> 如果指定了 AttatchDBFilename 和初始目录，并且给定的 MDF 文件存在，则调用 ObjectContext.DeleteDatabase 方法将删除的文件。<br /><br /> 如果在连接字符串使用且不存在 MDF 和初始目录不存在指定的 AttachDBFilename 值时调用 ObjectContext.DeleteDatabase，则该方法将引发 InvalidOperationException 异常。 以前，它会引发 SqlException 异常。|  
|建议|利用这些更改，可以更轻松地生成使用 DDL API 的工具和应用程序。 这些更改会影响以下方案中的应用程序兼容性：<br /><br /> 用户会编写代码，执行 DROP DATABASE 命令直接而不是调用 ObjectContext.DeleteDatabase ObjectContext.DatabaseExists 返回 true。 如果未附加数据库但存在 MDF 文件，则会中断现有代码。<br /><br /> 用户编写的期望 ObjectContext.DeleteDatabase 方法在 Initial Catalog 和 MDF 文件不存在时引发 SqlException 异常而不是收到 InvalidOperationException 异常的代码。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: MachineKey.Encode 和 MachineKey.Decode 方法现已过时  
  
|||  
|-|-|  
|详细信息|这些方法现在已过时。 调用这些方法的代码编译会产生编译器警告。|  
|建议|建议的备选项是[MachineKey.Protect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.protect\(v=vs.110\).aspx)和[MachineKey.Unprotect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx)。 或者，可以禁止显示生成警告，或通过使用较旧的编译器可避免它们。 Api 仍受支持。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> [MachineKey.Encode (字节\<xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|分析器|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29︰ 默认情况下禁用 OData Url 中的 Replace 方法  
  
|||  
|-|-|  
|详细信息|从.NET Framework 4.5 开始，默认情况下禁用 OData Url 中的替换方法。 当 OData 替换默认处于禁用状态 （现在） 时，包括 replace 函数 （即不常见） 的任何用户请求将失败。|  
|建议|如果是必需的 replace 方法 （即不常见），它可以通过重新启用[配置设置](https://msdn.microsoft.com/en-us/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx)。 但是，启用的 replace 方法可以打开安全漏洞，而且只应认真检查后使用。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|分析器|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: System.ServiceModel.Web.WebServiceHost 对象不再添加默认终结点  
  
|||  
|-|-|  
|详细信息|如果显式终结点都已由应用程序代码，则 System.ServiceModel.Web.WebServiceHost 对象将不再添加默认终结点。|  
|建议|如果用户希望能够连接到默认终结点和其他显式终结点已添加到的 WebServiceHost，应显式也将添加默认终结点 （使用 AddDefaultEndpoints）。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|分析器|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: EventSource.WriteEvent impls 必须传递 WriteEvent 同样它，再加上 ID) 接收的参数  
  
|||  
|-|-|  
|详细信息|运行时现在强制执行用于指定以下协定︰ 从定义的 ETW 事件方法的 EventSource 派生的类必须替换为事件 ID 跟 ETW 事件方法已传递的相同参数调用基类 EventSource.WriteEvent 方法。|  
|建议|如果讲述 EventSource 中读取数据违反此协定的事件源进程，引发 IndexOutOfRangeException 异常。|  
|范围|次要|  
|版本|4.5.1|  
|类型|运行时|  
|分析器|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: MinFreeMemoryPercentageToActiveService 现在考虑  
  
|||  
|-|-|  
|详细信息|此设置确定在可以激活 WCF 服务之前必须在服务器上可用的最小内存。 它旨在防止 OutOfMemoryException 异常。 在.NET Framework 4.5 中，此设置不起作用。 在.NET Framework 4.5.1 中，观察到的设置。|  
|建议|如果 Web 服务器上的可用内存少于由配置设置定义的百分比，将引发异常。 某些成功启动并且在受约束的内存环境中运行的 WCF 服务现在可能失败。|  
|范围|次要|  
|版本|4.5.1|  
|类型|运行时|  
|分析器|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: XmlTextReader DTD 实体扩展被限制为 10000000 个字符  
  
|||  
|-|-|  
|详细信息|DTD 实体扩展现已限制为 10000000 个字符。 加载不带 DTD 实体扩展或带有限的 DTD 实体扩展的 XML 文件不受影响。 包含了扩展到 10,000,000 个字符以上的 DTD 实体的文件将无法加载，且会立即引发异常。|  
|建议|值的 DTD 实体扩展限制是否过低 10000000，可以重写与[XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/en-us/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx)属性。 使用适当的 MaxCharactersFromEntity 值 XmlReaderSettings 可以传递给[XmlReader.Create](https://msdn.microsoft.com/en-us/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx)|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|分析器|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: XSLT 样式表的异常消息更改  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.5 中，XSLT 文件过于复杂时的错误消息文本为"样式表太复杂。" 在早期版本中，错误消息为“XSLT 编译错误”。 取决于错误消息的文本的应用程序代码将不再有效。 但是，异常类型保持不变，因此，此更改不会造成实际影响。|  
|建议|更新任何应用程序代码，具体取决于要从该错误状况 excepton 消息，需要新的消息，或 （甚至更好地） 更新代码以仅依赖于该异常类型 ([XsltException](https://msdn.microsoft.com/en-us/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx))，这仍是如此。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|[XslCompiledTransform.Load (MethodInfo、 字节\[\]，类型\<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|分析器|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: WF 序列化 Expressions.Literal<> \</> \> Datetime 现在以不同的方式 （将中断自定义 XAML 分析器）  
  
|||  
|-|-|  
|详细信息|关联[ValueSerializer](https://msdn.microsoft.com/en-us/library/system.windows.markup.valueserializer\(v=vs.110\).aspx)对象将转换的 DateTime 或 DateTimeOffset 对象的秒和毫秒分量都为非零和 （对于 DateTime 值） 其 DateTime.Kind 属性不是未指定为属性元素语法而不是一个字符串。 此更改允许在 DateTime 与 DateTimeOffset 值往返。 假定输入 XAML 是采用特性语法的自定义 XAML 分析器将无法正常运行。|  
|建议|此更改允许在 DateTime 与 DateTimeOffset 值往返。 假定输入 XAML 是采用特性语法的自定义 XAML 分析器将无法正常运行。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37︰ 在 WPF 的 PageRangeSelection 新枚举值  
  
|||  
|-|-|  
|详细信息|两个新成员 （CurrentPage 和 SelectedPage） 已添加到[PageRangeSelection](https://msdn.microsoft.com/en-us/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx)枚举。|  
|建议|在大多数情况下，这些更改不会影响用户代码。 取决于特定数目的元素中存在 Enum.GetNames 或 Enum.GetValues 的代码调用类型应修改，但 PageRangeSelection。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|分析器|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: WPF DispatcherSynchronizationContext.CreateCopy 现在将返回而不是当前实例的新副本  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4 中，DispatcherSynchronizationContext.CreateCopy() 主要作为一种性能优化返回与当前实例的引用。 在.NET Framework 4.5，该命令返回的新实例，这样就可以在第一次以得出的结论相等的引用指示正在执行的线程是正确的同步上下文中。  很可能会影响检查这些引用标识的代码，但由于此更改，应为.NET Framework 4.5 的迁移过程中测试调用 DispatcherSynchronizationContext.CreateCopy 的代码或更高版本。|  
|建议|请注意 DispatcherSynchronizationContext.CreateCopy() 现在将返回一个新的 SynchronizationContext 对象。  以前，用于生成这种方式引用的等效性的代码不实际上会检查是否已在正确的上下文中，但未生成针对.NET 4.5 或更高版本时。  尽管可能会导致出现问题，执行受影响的代码路径应足以确定是否这会带来任何问题。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|分析器|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: System.Threading.Tasks.Task 释放对象后不再引发 ObjectDisposedException  
  
|||  
|-|-|  
|详细信息|除了 Task.IAsyncResult.AsyncWaitHandle，System.Threading.Tasks.Task 方法不再引发 ObjectDisposedException 异常后释放该对象。<br />此更改支持缓存任务的使用。 例如，方法会返回一个缓存任务来表示已完成的操作，而不是分配新任务。 在以前的 .NET Framework 版本中无法执行此操作，因为任务的任何使用者都可以处置它（呈现为不可用）。|  
|建议|请注意，任务方法可能不再引发 ObjectDisposedExceptions 在情况下当释放该对象。 如果应用程序本来想知道任务已处理此异常，它应更新显式地检查任务的状态使用[Task.Status](https://msdn.microsoft.com/en-us/library/system.threading.tasks.task.status\(v=vs.110\).aspx)。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40︰ 不同的异常处理 ObjectContext.CreateDatabase 和 DbProviderServices.CreateDatabase 方法  
  
|||  
|-|-|  
|详细信息|从.NET 4.5 开始，如果数据库创建失败，`CreateDatabase`方法将尝试删除空数据库。 如果该操作成功，原始`SQLException`将传播 (而不是`InvalidOperationException`时始终引发在.NET 4.0)|  
|建议|如果在执行 ObjectContext.CreateDatabase 或 DbProviderServices.CreateDatabase 时捕捉 InvalidOperationException，SQLExceptions 应现在还捕捉。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|分析器|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: ObjectContext.Translate 和 ObjectContext.ExecuteStoreQuery 现在支持枚举类型  
  
|||  
|-|-|  
|详细信息|在.NET 4.0 中，泛型参数`T`的`ObjectContext.Translate`和`ObjectContext.ExecuteStoreQuery`方法找不到枚举。 现在支持这种情况。|  
|建议|如果在.NET 4.0 中的枚举类型上调用了翻译或 ExecuteStoreQuery，返回"0"。 如果该行为是理想的则应使用常数 0 （或它的 enum 等效项） 替换该调用。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|[ObjectContext.ExecuteStoreQuery<>\>(字符串、 对象\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [ObjectContext.ExecuteStoreQuery<>\>(字符串、 字符串、 MergeOption，对象\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|分析器|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: Enumerable.Empty<> \</> \>始终返回的缓存实例  
  
|||  
|-|-|  
|详细信息|从.NET 4.5 开始`Enumerable.Empty`始终返回缓存的内部实例`IEnumerable<T>`。<br /><br /> 以前，`Enumerable.Empty`将缓存为空`IEnumerable<T>`时调用 API 时，也就是说，在某些情况下在其中`Enumerable.Empty`调用快速和并发，不同类型的实例可能会返回对 API 的不同调用的。|  
|建议|以前的行为是不确定的因为代码是不太可能依赖于它。 但是，最可能的情况下，空的可枚举接口进行比较和预期为有时不相等，显式的空数组应在创建 (`new T[0]`) 而不是使用`Enumerable.Empty`。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|分析器|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: HttpRequest.ContentEncoding 属性禁止 UTF7  
  
|||  
|-|-|  
|详细信息|从.NET Framework 4.5 开始，utf-7 编码禁止 HttpRequests' 正文中。 在某些情况下，取决于传入的 UTF-7 数据的应用程序数据将不会正确解码。|  
|建议|理想情况下，应用程序应更新为不使用在 HttpRequests utf-7 编码。 或者，通过使用还原旧行为`aspnet:AllowUtf7RequestContentEncoding`属性[appSettings](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx)元素。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|分析器|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: HttpUtility.JavaScriptStringEncode 转义 and 符  
  
|||  
|-|-|  
|详细信息|从.NET Framework 4.5 开始，JavaScriptStringEncode 字符进行转义 and 符 （&）。|  
|建议|如果您的应用程序依赖于此方法的以前的行为，可以添加到 aspnet:JavaScriptDoNotEncodeAmpersand 设置[ASP.NET appSettings 元素](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx)配置文件中。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|分析器|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46︰ 讲述将截断带有嵌入的 null 字符串  
  
|||  
|-|-|  
|详细信息|讲述将截断带有嵌入的 null 字符串。 EventSource 类不支持 null 字符。 此更改仅影响应用程序使用讲述读取过程中的 EventSource 数据并且 null 字符用作分隔符。|  
|建议|EventSource 数据应更新，如有可能，为不使用嵌入的空字符。|  
|范围|边缘|  
|版本|4.5.1|  
|类型|运行时|  
|受影响的 Api|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName> \</String, String>|  
|分析器|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: ObsoleteAttribute WinMD 方案中将导出为 ObsoleteAttribute 和 DeprecatedAttribute  
  
|||  
|-|-|  
|详细信息|当您创建 Windows 元数据数据库 （.winmd 文件） 时，将作为 ObsoleteAttribute 和 Windows.Foundation.DeprecatedAttribute 导出 ObsoleteAttribute 特性。|  
|建议|对使用 ObsoleteAttribute 特性的现有源代码进行重新编译可能会生成警告，当使用该代码在 C + + /CX 或 JavaScript。<br /><br /> 我们不建议将 ObsoleteAttribute 和 Windows.Foundation.DeprecatedAttribute 应用于托管程序集; 中的代码它可能会导致生成警告。|  
|范围|边缘|  
|版本|4.5.1|  
|类型|重定目标|  
|分析器|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49︰ 对具有不正确的体系结构的依赖关系现在警告 ResolveAssemblyReference 任务  
  
|||  
|-|-|  
|详细信息|此任务发出警告 MSB3270，它表示引用或任何依赖项不匹配应用程序的体系结构。 例如，这情况时发生︰ 使用 anycpu 选项已编译应用程序包括 x86 引用。 这样的情况可能导致运行时应用失败（在本例中为，如果应用部署为 x64 过程）。|  
|建议|有两方面的影响：<br /><br /> 重新编译将生成警告，当应用在以前版本的 MSBuild 下编译时，此类警告未显示。 但是，由于该警告可标识运行时失败可能的来源，所以应该调查并处理它。<br /><br /> 如果警告被视为错误，则应用将无法进行编译。|  
|范围|次要|  
|版本|4.5.1|  
|类型|重定目标|  
|分析器|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: WPF 文本框默认情况下撤消限制为 100  
  
|||  
|-|-|  
|详细信息|在.NET 4.5 中，WPF 文本框的默认撤消限制是 100 （而不是在.NET 4.0 中不受限制）|  
|建议|如果撤消限制 100 得太低，可以显式设置了限制与文本框的 UndoLimit 属性|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|分析器|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55︰ 不再在终结器线程上传播期间 System.Threading.Tasks.Task 中未观察到处理的异常  
  
|||  
|-|-|  
|详细信息|因为 System.Threading.Tasks.Task 类表示一个异步操作，它捕获在异步处理过程中发生的所有非严重异常。 在.NET Framework 4.5 中，如果未观察到异常，并且您的代码永远不会等待任务，该异常将不再在终结器线程上传播并在垃圾回收期间导致进程崩溃。 此更改增强了使用任务类执行未观察到的异步处理的应用程序的可靠性。|  
|建议|如果应用程序依赖于未观察到的异步异常传播到终结器线程，可以通过提供相应的处理程序的还原之前的行为[TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/en-us/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx)事件，或通过设置[运行时配置元素](https://msdn.microsoft.com/en-us/library/jj160346%28v=vs.110%29.aspx)。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|分析器|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: IAsyncResult.CompletedSynchronously 属性必须是正确的生成完成的任务  
  
|||  
|-|-|  
|详细信息|在调用时 TaskFactory.FromAsync，IAsyncResult.CompletedSynchronously 属性的实现必须是正确的生成完成的任务。 也就是说，属性必须返回 true，当且仅当同步完成实现。 之前，属性未被选中。|  
|建议|如果返回的 IAsyncResult 实施正确 CompletedSynchronusly 属性仅当已同步完成的任务，则返回 true，然后将会按时不换行。 用户应检查其所拥有 （如果有） 以确保它们正确评估是否同步或未完成的任务的 IAsyncResult 实施。|  
|范围|边缘|  
|版本|4.5|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> </TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult>|  
|分析器|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: ObjectContext.CreateDatabase 方法创建的日志文件名称已更改以匹配 SQL Server 规范  
  
|||  
|-|-|  
|详细信息|当 CreateDatabase 方法调用直接或通过使用 Code First 与 SqlClient 提供程序和连接字符串中的 AttachDBFilename 值，它将创建日志文件命名 filename_log.ldf 而不是 filename.ldf （其中，filename 是 AttachDBFilename 值所指定的文件的名称）。 此更改通过提供根据 SQL Server 规范命名的日志文件来改进调试。|  
|建议|如果日志文件名称很重要的应用程序的应更新应用程序需要标准 _log.ldf 文件名的格式。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|分析器|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: Page.LoadComplete 事件不再导致 System.Web.UI.WebControls.EntityDataSource 控件来调用数据绑定  
  
|||  
|-|-|  
|详细信息|`Page.LoadComplete`事件不再导致 System.Web.UI.WebControls.EntityDataSource 控件来调用对 create/update/delete 参数的更改的数据绑定。 此更改消除到数据库的外来行程，防止控件的值重置，并生成与其他数据控件，如 SqlDataSource 和对象数据源保持一致的行为。 在应用程序依赖于在 `Page.LoadComplete` 事件中调用数据绑定的极少数情况下，此更改会产生不同的行为。|  
|建议|如果数据绑定的需要，手动调用的事件中早在后期后面的数据绑定。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: WebUtility.HtmlDecode 不再对无效输入的序列进行解码  
  
|||  
|-|-|  
|详细信息|默认情况下，解码方法不再将无效的输入序列解码为无效的 UTF-16 字符串。 相反，它们将返回原始的输入。|  
|建议|仅当你存储二进制数据而不是字符串中的 UTF-16 数据时，解码器输出中的更改才会起作用。 若要显式控制此行为，请设置`aspnet:AllowRelaxedUnicodeDecoding`属性[appSettings](https://msdn.microsoft.com/en-us/library/ms228154\(v=vs.110\).aspx)元素设置为 true 将启用旧行为，或为 false，以允许当前行为。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|分析器|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63︰ 通过 ClickOnce 发布的应用程序使用 sha-256 代码签名证书在 Windows 2003 上可能会失败  
  
|||  
|-|-|  
|详细信息|使用 SHA256 对可执行文件签名。 以前，无论代码签名证书是 SHA-1 还是 SHA-256，都使用 SHA1 进行签名。 这适用于：<br /><br /> 使用 Visual Studio 2012 或更高版本生成的所有应用程序。<br /><br /> 使用 Visual Studio 2010 或更早版本在安装了 .NET Framework 4.5 的系统上生成的应用程序。<br /><br /> 此外，如果安装了 .NET Framework 4.5 或更高版本，则 ClickOnce 清单也会采用 SHA-256 签名，因为 SHA-256 证书与编译所采用的 .NET Framework 版本无关。|  
|建议|签名 ClickOnce 可执行文件进行更改仅影响 Windows Server 2003 系统;它们需要安装 KB 938397。<br /><br /> 即使应用是面向 .NET Framework 4.0 或早期版本，对使用 SHA-256 签名的清单进行更改，将引入依赖 .NET Framework 4.5 或更高版本的运行时。|  
|范围|边缘|  
|版本|4.5-4.6|  
|类型|重定目标|  
|分析器|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision 和 DbParameter.Scale 现在是虚拟的公共成员  
  
|||  
|-|-|  
|详细信息|DbParameter.Precision 和 DbParameter.Scale 实现为公共虚拟属性。 它们替换相应的显式接口实现、 DbParameter.IDbDataParameter.Precision 和 DbParameter.IDbDataParameter.Scale。|  
|建议|当重新构建 ADO.NET 数据库提供程序，这些差异将要求要应用于精度和小数位数的属性的替代关键字。 这才被必需时重新生成组件;现有的二进制文件将继续工作。|  
|范围|次要|  
|版本|4.5.1|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|分析器|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData 现在将数据检索为 utf-8  
  
|||  
|-|-|  
|详细信息|对于面向.NET Framework 4 或.NET Framework 4.5.1 或更早版本上运行的应用程序，DataObject.GetData 为 ASCII 字符串检索 HTML 格式的数据。 因此，非 ASCII 字符（ASCII 代码大于 0x7F 的字符）由两个随机字符表示。<br /><br /> 用于面向.NET Framework 4.5 或更高版本且在.NET Framework 4.5.2 上运行的应用程序`DataObject.GetData`将 HTML 格式的数据检索为 utf-8，它可正确代表大于 0x7F 的字符。|  
|建议|如果你实现使用 HTML 格式的字符串编码问题解决方法 （例如，通过显示编码从剪贴板将其传递给 UTF8Encoding.GetString 方法检索的 HTML 字符串），并且正在重定目标从版本 4 为 4.5 应用程序，应删除该解决方法。<br /><br /> 如果由于某种原因需要这一旧行为，则该应用程序可以面向.NET Framework 4.0，若要获得该行为。|  
|范围|边缘|  
|版本|4.5.2|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|分析器|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: TargetFrameworkName 默认应用程序域不再默认为 null，如果未设置  
  
|||  
|-|-|  
|详细信息|TargetFrameworkName 以前在为空，默认应用程序域，除非显式设置。 从开始 4.6 中，默认应用程序域的 TargetFrameworkName 属性将具有默认值 （如果有的话） 从 TargetFrameworkAttribute 派生。 非默认应用程序域将继续从默认应用程序域 （这不会默认为 null 4.6 中） 继承其 TargetFrameworkName，除非显式重写。|  
|建议|应更新代码，以便不依赖于`AppDomainSetup.TargetFrameworkName`默认设置为 null。 如果需要，此属性将继续进行的计算结果为 null，它可以显式设置为该值。|  
|范围|边缘|  
|版本|4.6|  
|类型|运行时|  
|受影响的 Api|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|分析器|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: X509Certificate2.ToString(bool) 并不会引发现在当.NET 不能处理证书  
  
|||  
|-|-|  
|详细信息|以前，如果此方法将引发为 verbose 参数传递 'true'，且存在未安装的证书不支持的.Net Framework。 现在，该方法将失败，并且返回省略 certifiate 无法访问某些部分的有效字符串。|  
|建议|应更新 X509Certificate2.ToString(bool) 根据任何代码，以便在某些情况下，在其中 API 之前引发预期返回的字符串可能排除了某些证书数据 （如公钥、 私钥和扩展）。|  
|范围|边缘|  
|版本|4.6|  
|类型|运行时|  
|受影响的 Api|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|分析器|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77︰ 反射对象无法再从托管代码向进程外 DCOM 客户传递  
  
|||  
|-|-|  
|详细信息|反射对象可能无法再从托管代码传道至进程外客户端 受以下类型︰<br /><br /> Assembly<br /><br /> MemberInfo （和其派生的类型，包括 FieldInfo、 MethodInfo、 类型和类型信息）<br /><br /> MethodBody<br /><br /> 模块<br /><br /> ParameterInfo。<br /><br /> 调用`IMarshal`为对象返回`E_NOINTERFACE`。|  
|建议|更新封送处理代码以使用非反射对象|  
|范围|次要|  
|版本|4.6|  
|类型|运行时|  
|分析器|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition Datetime 返回稍有不同的字符串  
  
|||  
|-|-|  
|详细信息|已更新 ContentDispositions 的字符串表示形式，开始在 4.6，以始终表示为具有两位数的日期时间的小时数部分。 这是为了符合[RFC822](http://www.ietf.org/rfc/rfc0822.txt)和[RFC2822](http://www.ietf.org/rfc/rfc2822.txt)。 这将导致`ContentDisposition.ToString`返回其中的处理时间元素之一是在上午 10:00 之前 4.6 在方案中的略有不同的字符串。 请注意通过将它们转换为字符串，因此应查看任何 ContentDisposition ToString 操作、 序列化或 GetHashCode 调用 ContentDispositions 有时序列化。|  
|建议|不需要从不同的.NET Framework 版本的字符串表示形式 ContentDispositions 将正确地比较到另一个。 将字符串转换回为 ContentDispositions，如果可能之前进行比较。|  
|范围|次要|  
|版本|4.6|  
|类型|运行时|  
|受影响的 Api|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|分析器|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: WorkflowDesigner.Load 并不会删除符号属性  
  
|||  
|-|-|  
|详细信息|如果目标.NET Framework 4.5 中的工作流设计器中，并使用 WorkflowDesigner.Load() 方法加载重新承载的 3.5 工作流，XamlDuplicateMemberException 保存该工作流时引发。|  
|建议|此 bug 只表现在工作流设计器中，面向.NET Framework 4.5，因此它可以通过设置解决时`WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName`4.0 版的.NET framework。<br /><br /> 或者，可以通过使用避免此问题[WorkflowContext.Load(string)](https://msdn.microsoft.com/en-us/library/ee425926\(v=vs.110\).aspx)方法以加载该工作流，而不是[WorkflowDesigner.Load()](https://msdn.microsoft.com/en-us/library/ee403482\(v=vs.110\).aspx)。|  
|范围|主要|  
|版本|4.5-4.5.2|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|分析器|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: SqlConnection.Open 无法在 Windows 7 上与非 IFS Winsock BSP 或 LSP 存在  
  
|||  
|-|-|  
|详细信息|SqlConneciton.Open 和 OpenAsync 失败.NET Framework 4.5 中，如果计算机上存在非 IFS Winsock BSP 或 LSP 的 Windows 7 计算机上运行。<br /><br /> 若要确定是否已安装非 IFS BSP 或 LSP，请使用`netsh WinSock Show Catalog`命令，并检查每个`Winsock Catalog Provider Entry`返回的项。 如果服务标志值具有`0x20000`并设置位，该提供程序使用 IFS 句柄，将正常工作。 如果`0x20000`位被清除 （未设置），它是一个非 IFS BSP 或 LSP。|  
|建议|此 bug 已修复.NET Framework 4.5.2 中，因此它可以避免通过升级.NET Framework。 或者，它可以通过删除任何已安装非-IFS Winsock Lsp 避免。|  
|范围|次要|  
|版本|4.5-4.5.2|  
|类型|运行时|  
|受影响的 Api|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|分析器|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84︰ 在.NET 4.5 中 ICommand.CanExecuteChanged 事件行为更改  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.5 中，CanExecuteChangedEvent 已被忽略，除非该事件的发件人是与引发事件的对象相同的对象。 在.NET Framework 4.5 servcing 更新已修复此 bug。|  
|建议|此 bug 已修复在.NET Framework 4.5 中服务的版本中，因此它可以避免通过确保.NET Framework 最新或通过升级到.NET Framework 4.5.1。 或者，可以修改应用程序代码中使用 ICommand，若要确保发件人在引发 CanExecuteChanged 命令时引发事件的对象相同。|  
|范围|次要|  
|版本|4.5-4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|分析器|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85︰ 某些.NET Api 会导致 （处理） 的第一次机会 EntryPointNotFoundExceptions  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.5、.NET 方法的一小部分开始引发第一次机会 EntryPointNotFoundExceptions。 这些异常的处理在.Net Framework 中，但可能会破坏意料之外第一机会异常的测试自动化。 启用 HighVersionLie 后，这些相同的 Api 会破坏某些 ApiVerifier 方案。|  
|建议|通过升级到.NET Framework 4.5.1，可以避免此错误。 或者，可以更新测试自动化，若要在首次 EntryPointNotFoundExceptions 不中断。|  
|范围|边缘|  
|版本|4.5-4.5.1|  
|类型|运行时|  
|受影响的 Api|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> [Debug.Assert (布尔值、 字符串、 字符串、 对象\<xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|分析器|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: WPF TreeView 或分组列表框中 VirtualizingStackPanel 滚动可能导致挂起  
  
|||  
|-|-|  
|详细信息|在.NET Framework&4;.5 版中，滚动 WPF TreeView 虚拟化的堆栈面板中会导致挂起中是否存在边距视区 （例如，树视图中或在 ItemsPresenter 元素上的项） 之间。 此外，在某些情况下，视图中的不同大小的项会导致不稳定即使有无边距。|  
|建议|通过升级到.NET Framework 4.5.1，可以避免此错误。 或者，边距可以从查看集合 （如 Treeview) 虚拟化的堆栈面板中删除所有包含的项是否相同的大小。|  
|范围|主要|  
|版本|4.5-4.5.1|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|分析器|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom 返回错误的结果，对于具有约束的泛型变量  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.5 中，Type.IsAssignableFrom 错误地返回`false`在所有情况下，对于某些泛型类型约束。|  
|建议|在服务更新已解决此问题。 请更新.NET Framework 4.5，或升级到.NET Framework 4.5.1 或更高版本，若要解决此问题。 另外，避免将与具有泛型参数约束的泛型类型一起使用来。 反射 Api 可用来解决。|  
|范围|次要|  
|版本|4.5-4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|分析器|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: EntityFramework 6.0 从 Visual Studio 启动的应用程序中加载速度非常缓慢  
  
|||  
|-|-|  
|详细信息|启动使用 EntityFramework 6.0 的 Visual Studio 2013 中应用程序可能会很慢。|  
|建议|在 EntityFramework 6.0.2 中修复此问题。 请更新 EntityFramework 以避免性能问题。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92︰ 时使用 AntiXSSEncoder 更改多行 ASP.Net TextBox 间距  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.0 中，额外的行插入行之间的多行文本框在回发时，如果使用`AntiXSSEncoder`。 在.NET Framework 4.5 中，那些多余的换行符不包含在内，但只有当 web 应用程序面向的.NET 4.5|  
|建议|请注意 4.0 为.NET 4.5 重定目标的 web 应用程序可能有多行文本框中改进，这不会再插入额外的换行。 如果这不是理想的应用程序可以让这一旧行为，通过定向.NET Framework 4.0 在.NET Framework 4.5 上运行时。|  
|范围|次要|  
|版本|4.5|  
|类型|重定目标|  
|分析器|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue<>\>。TryPeek 可以通过其输出参数返回一个错误 null  
  
|||  
|-|-|  
|详细信息|在某些多线程的情况下，`ConcurentQueue<T>.TryPeek`可以返回 true，但使用具有 null 值 （而不是正确的扫视值） 为 out 参数进行填充。|  
|建议|在.NET Framework 4.5.1 中解决此问题。 升级到此框架来解决此问题。|  
|范围|主要|  
|版本|4.5-4.5.1|  
|类型|运行时|  
|受影响的 Api|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|分析器|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98︰ 单个 TableLayoutPanel 单元格中的多个项目可能会重新排列  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.5 中，如果多个项放在同一个 TableLayoutPanel 单元格中，它们可能会显示不同的顺序不是它们在.NET Framework 4.0 中一样。|  
|建议|.NET Framework 4.5 的情况下，此行为已还原服务更新中。 请更新.NET Framework 4.5，或升级到.NET Framework 4.5.1 或更高版本，若要解决此问题。 另外，避免在同一个 TableLayourPanel 单元格中的多个项目的不明确的用例。|  
|范围|次要|  
|版本|4.5-4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|分析器|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: Foreach 迭代器变量的作用域现在在迭代期内，因此闭包捕获语义不同 （在 C#&5;)  
  
|||  
|-|-|  
|详细信息|从 C# 5 (Visual Studio 2012) 开始，foreach 迭代器变量的范围是在迭代期内。 如果代码以前根据变量不包括在 foreach 的闭包中，这会导致中断。 此更改的症状将传递给 delagate 的迭代器变量将被视为在创建了委托，而不是在调用委托时的值时的值。|  
|建议|理想情况下，应更新代码需要新的编译器行为。 如果旧的语义是必需的可以使用单独的显式放置在循环的范围之外的变量替换迭代器变量。|  
|范围|主要|  
|版本|4.5|  
|类型|重定目标|  
|分析器|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: HtmlTextWriter 不能呈现\`<br>\>元素正确  
  
|||  
|-|-|  
|详细信息|开始在.NET Framework 4.6 中，调用`HtmlTextWriter.RenderBeginTag()`和`HtmlTextWriter.RenderEndTag()`与`<BR />`元素正确插入只有一个`<BR />`（而不是两个）|  
|建议|如果应用程序依赖于额外`<BR />`标记中，`HtmlTextWriter.RenderBeginTag()`应调用第二次。 请注意，此行为更改仅影响面向的.NET Framework 4.6，因此，另一个选项是为了获得原有的行为面向以前版本的.NET framework 的应用程序。|  
|范围|边缘|  
|版本|4.6|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|分析器|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104︰ 调用 Items.Refresh WPF ListBox、 ListView 或具有选定项的数据网格上可能会导致要显示在元素中的重复项  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.5 中，在列表框中选择项目时从代码调用 ListBox.Items.Refresh 会导致在列表中复制所选的项目。 ListView 和 DataGrid 出现类似问题。 这是在.NET Framework 4.6 中固定的。|  
|建议|通过以编程方式调用刷新之前取消选择项并在调用完成后再重新选择它们，可能会解决此问题。 或者，此问题已在.NET Framework 4.6 中修复，并可以通过升级到该版本的.NET Framework 进行寻址。|  
|范围|次要|  
|版本|4.5-4.6|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|分析器|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: ETW EventListeners 不会捕获来自提供商提供了显式关键字 （例如 TPL 提供商） 的事件  
  
|||  
|-|-|  
|详细信息|具有空白关键字掩码 ETW EventListeners 不正确捕获来自提供商提供了显式关键字的事件。 在.NET Framework 4.5 中，TPL 提供程序从开始提供显式的关键字，触发此问题。 在.NET Framework 4.6，已更新 EventListeners 不再具有此问题。|  
|建议|若要解决此问题，将对 EnableEvents (eventSource，级别) 的调用替换对显式指定要使用的"任何关键字"蒙板的 EnableEvents 重载的调用︰ `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`。<br /><br /> 或者，此问题已在.NET Framework 4.6 中修复，并可以通过升级到该版本的.NET Framework 进行寻址。|  
|范围|边缘|  
|版本|4.5-4.6|  
|类型|运行时|  
|受影响的 Api|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|分析器|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109︰ 构建 edmx Entity Framework Visual Studio 2013 可能会失败，错误 MSB4062 如果使用 EntityDeploySplit 或 EntityClean 任务  
  
|||  
|-|-|  
|详细信息|MSBuild 12.0 工具 （包括 Visual Studio 2013 中） 更改 msbuild 文件的位置，从而导致较旧的实体框架的目标文件无效。 结果是，`EntityDeploySplit`和`EntityClean`任务失败，因为它们是找不到`Microsoft.Data.Entity.Build.Tasks.dll`。 请注意，此分页符不由于工具集 (msbuild/VS) 发生变化，因为.NET Framework 发生了更改。 才会在不是在仅升级.NET Framework 时升级开发人员工具。|  
|建议|实体框架的目标文件已修复，以使用.NET Framework 4.6 中新的 msbuild 布局起点。 升级到该版本的 Framework 将解决这个问题。 或者，[这](http://stackoverflow.com/a/24249247/131944)解决方法可用于直接修补程序的目标文件。|  
|范围|主要|  
|版本|4.5.1-4.6|  
|类型|重定目标|  
|分析器|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: XSD 架构验证现在是否正确检测到违反唯一约束如果使用复合键，并且有一个键为空  
  
|||  
|-|-|  
|详细信息|.NET Framework 4.6 之前的版本有错误导致 XSD 验证以不检测对复合键的唯一约束，如果在某个键为空。 在.NET Framework 4.6，解决此问题。 这将导致更正确的验证，但也可能会导致不验证就以前会使一些 XML。|  
|建议|如果更松散，需要.NET Framework 4.0 验证，验证应用程序可以面向版本 4.5 （或更早版本） 的.NET framework。 当重定目标到.NET 4.6，但是，应完成代码评审以确保，重复的复合键 （如在这个问题的描述中所述） 不会验证。|  
|范围|边缘|  
|版本|4.6|  
|类型|重定目标|  
|分析器|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112︰ 索引器属性的调用 Attribute.GetCustomAttributes 不再引发 AmbiguousMatchException，如果可以按索引的类型解析多义性  
  
|||  
|-|-|  
|详细信息|.NET Framework 4.6 中，调用之前`GetCustomAttribute(s)`在索引器属性只是在索引的类型不同于另一个属性，该属性将导致`AmbiguousMatchException`。 从.NET Framework 4.6 开始，该属性将正确返回特性。|  
|建议|请注意，GetCustomAttribute(s) 将正常工作更频繁地现在。 如果应用程序以前依赖`AmbiguousMatchException`，现在应使用反射来显式改为查找多个索引器。|  
|范围|边缘|  
|版本|4.6|  
|类型|运行时|  
|受影响的 Api|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|分析器|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113︰ 间歇性地无法滚动到底部项 （如列表框和 DataGrid） 的 Itemscontrol 中使用自定义 Datatemplate 时  
  
|||  
|-|-|  
|详细信息|在某些情况下，.NET Framework 4.5 中的 bug 导致 （如列表框、 组合框、 DataGrid 等） 的 Itemscontrol 不滚动到底部项时使用自定义 Datatemplate。 如果滚动尝试第二次 （滚动后重新启动），则它将再运行。|  
|建议|此问题已在.NET Framework 4.5.2 中修复，并且可以通过升级到.NET Framework 的版本 （或更高版本） 进行寻址。 或者，用户可以仍将滚动条拖至这些集合中的最后一个项，但可能需要进行两次尝试成功执行此操作。|  
|范围|次要|  
|版本|4.5-4.5.2|  
|类型|运行时|  
|分析器|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: GlyphRun.ComputeInkBoundingBox() 和 FormattedText.Extent 返回开头在.NET 4.5 中的不同值。  
  
|||  
|-|-|  
|详细信息|都进行了改进 GlyphRun.ComputeInkBoundingBox() 和 FormattedText.Extent 以解决问题的.NET Framework 4.5 中对应的框是太小，在某些情况下，.NET Framework 4.0 中包含的标志符号。 因此，某些边界框将为较大开始在.NET Framework 4.5 中，导致 UI 布局细微的差异。|  
|建议|请注意，某些标志符号边界框的大小已增加。 这些更改通常如何改善演示文稿和命中的框测试，但如果需要较旧的 (预.NET 4.5) 行为时，它可以将选择加入通过将以下条目添加到 app.config 文件︰<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|分析器|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124︰ 从 CellEditEnding 处理程序调用 DataGrid.CommitEdit 删除焦点  
  
|||  
|-|-|  
|详细信息|从一个 DataGrid 的 CellEditEnding 事件处理程序调用 DataGrid.CommitEdit 会导致失去焦点的 DataGrid。|  
|建议|此 bug 已修复.NET Framework 4.5.2 中，因此它可以避免通过升级.NET Framework。 或者，它可以通过显式调用 CommitEdit 后重新选择 DataGrid 避免。|  
|范围|边缘|  
|版本|4.5-4.5.2|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|分析器|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC 现在转义通过路由参数中传递的字符串中的空格  
  
|||  
|-|-|  
|详细信息|若要符合 RFC 2396，路由路径中的空格填充从一个路由操作参数时现在转义。 因此，而`/controller/action/some data`以前将匹配路由`/controller/action/{data}`，并提供`some data`数据参数，它现在将提供`some%20data`相反。|  
|建议|要恢复原义字符串参数，从一个路由，应更新代码。 如果需要原始 URI，则可以使用 Request.RequestUri.OriginalString API 访问。|  
|范围|次要|  
|版本|4.5.2|  
|类型|运行时|  
|受影响的 Api|<xref:System.Web.Http.RouteAttribute.%23ctor%28System.String%29?displayProperty=fullName>|  
|分析器|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET 不再支持部分命名空间限定的 System.Windows Api  
  
|||  
|-|-|  
|详细信息|从.NET 4.5.2 开始，VB.NET 项目中不能指定 System.Windows Api 中，使用部分限定的命名空间。 例如，指`Windows.Forms.DialogResult`将失败。 相反，代码必须引用的完全限定名 (`System.Windows.Forms.DialogResult`) 或导入特定的命名空间，并只需引用`DialogResult`。|  
|建议|应更新代码以引用`System.Windows`Api 使用简单名称 （和导入相关的命名空间） 或完全限定的名称。|  
|范围|次要|  
|版本|4.5.2|  
|类型|重定目标|  
|分析器|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>不得超过&129;︰ 不支持对具有非公共 setter 的属性的双向数据绑定  
  
|||  
|-|-|  
|详细信息|尝试将数据绑定到无公共 setter 属性从未如此受支持的方案。 从开始在.NET Framework 4.5.1 中，这种情况下将引发 InvalidOperationException。 请注意，仅用于专门面向.NET Framework 4.5.1 的应用程序会引发此新的异常。 如果应用是面向.NET Framework 4.5，则将允许的调用。 如果应用程序不面向特定的.NET Framework 版本，绑定将被处理为单向。|  
|建议|应更新应用程序使用单向绑定，或公开公开属性的 setter。 或者，使面向.NET Framework 4.5 将导致应用程序以表现出这一旧行为。|  
|范围|次要|  
|版本|4.5.1|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|分析器|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: Marshal.SizeOf 和 Marshal.PtrToStructure 重载中断动态代码  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.5.1 中动态绑定到的方法开始`Marshal.SizeOf`或`Marshal.PtrToStructure`（通过 Windows PowerShell、 IronPython 或 C# 动态关键字，例如） 可能会导致`MethodInvocationExceptions`由于已添加这些方法的新重载，可能不明确到脚本引擎。|  
|建议|更新脚本以清楚地指示使用哪个重载应该为。 通常由显式地强制转换为这些方法的类型参数，就可以`System.Type`。 请参阅[此链接](https://support.microsoft.com/en-us/kb/2909958/)的更多详细信息和示例说明了如何变通解决该问题。|  
|范围|次要|  
|版本|4.5.1|  
|类型|运行时|  
|分析器|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131︰ 如果其处理程序显示 Windows 窗体消息框中反复调用 PreviewLostKeyboardFocus  
  
|||  
|-|-|  
|详细信息|开始在.NET Framework 4.5 中，调用`System.Windows.Forms.MessageBox.Show`从`UIElement.PreviewLostKeyboardFocus`处理程序将导致重新时要触发消息框关闭，可能会导致无限循环的消息框的处理程序。|  
|建议|若要解决此问题的两个选项<br /><br /> 它可能会避免通过调用`System.Windows.MessageBox.Show`而不是`System.Windows.Forms.MessageBox.Show`。<br /><br /> 可能通过显示消息框中的来避免`LostKeyboardFocus`事件处理程序 (而不是`PreviewLostKeyboardFocus`事件处理程序)。|  
|范围|边缘|  
|版本|4.5|  
|类型|运行时|  
|受影响的 Api|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|分析器|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133︰ 在 ConcurrentDictionary netdatacontractserializer 在.NET 4.5 中序列化无法反序列化.net 4.5.1 或 4.5.2  
  
|||  
|-|-|  
|详细信息|由于对该类型的内部更改`System.Collections.Concurrent.ConcurrentDictionary`用.NET Framework 4.5 进行序列化的对象使用`NetDataContractSerializer`不能在.NET Framework 4.5.1 或.NET Framework 4.5.2 中反序列化。<br /><br /> 请注意移动另一个方向 (使用.NET Framework 进行序列化 4.5.x 和反序列化.NET Framework 4.5) 的工作。 同样，与.NET Framework 4.6 所有 4.x 跨版本序列化都配合使用。<br /><br /> 不会影响序列化和反序列化与.NET Framework 的单个版本。|  
|建议|如有必要进行序列化和反序列化.NET Framework 4.5 和.NET Framework 4.5.1/4.5.2 之间 ConcurrentDictionary，如 DataContractSerializer 或 BinaryFormatter 序列化程序的备用序列化来代替 NetDataContractSerializer。<br /><br /> 或者，在.NET Framework 4.6 中解决此问题，因为它可能会通过升级到该版本的.NET Framework 解决。|  
|范围|次要|  
|版本|4.5.1-4.6|  
|类型|运行时|  
|分析器|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134︰ 波斯历现在使用回历太阳能算法  
  
|||  
|-|-|  
|详细信息|从.NET Framework 4.6，波斯历类使用回历太阳能算法。 转换之间波斯历和其他日历的日期可能会产生一个略有不同的结果以开头的.NET Framework 4.6 表示的日期早于 1800年或晚于 2023 （公历）。<br /><br /> 此外，`PersianCalendar.MinSupportedDateTime`现`March 22, 0622 instead of March 21, 0622`。|  
|建议|请注意，在.NET 4.6 中使用波斯历时，某些早或最晚日期可能会稍有不同。 此外，在序列化可能在不同版本的.NET Framework 运行的进程之间的日期，请不以存储波斯历日期字符串 （因为这些值可能不同）。|  
|范围|次要|  
|版本|4.6|  
|类型|运行时|  
|受影响的 Api|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|分析器|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138︰ 使用空参数调用 CreateDefaultAuthorizationContext 已更改  
  
|||  
|-|-|  
|详细信息|为调用所返回的 AuthorizationContext 实现`CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)`与 null authorizationPolicies 参数已更改其在.NET Framework 4.6 中的实现。|  
|建议|在极少数情况下，使用自定义身份验证的 WCF 应用可能会看到行为差异。 在这种情况下，可以在两种方法之一还原之前的行为︰<br /><br /> 重新编译你的应用以面向早于 4.6 的 .NET Framework 版本。 对于 IIS 承载的服务，使用<httpRuntime targetframework="x.x"></httpRuntime>\>元素以面向.NET Framework 的早期版本。<br /><br /> 添加以下代码行到`<appSettings>`app.config 文件的部分︰`<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`|  
|范围|次要|  
|版本|4.6|  
|类型|重定目标|  
|受影响的 Api|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|分析器|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141︰ 必须在 TreeView 中使用 WPF TreeViewItem  
  
|||  
|-|-|  
|详细信息|限制外部 TreeView TreeViewItem 元素的使用情况的 4.5 中引入了更改。 这种情况在以下情况下︰<br /><br /> TreeViewItem 的可视父级不是一个面板。 （为 TreeView 生成 TreeViewItem 将有一个面板作为其父级）<br /><br /> TreeViewItem 是 VirtualizingStackPanel 充当"项 host"为列表控件 （列表框、 DataGrid、 ListView 等） 的后代。 虚拟化不需要进行启用。<br /><br /> VirtualizingStackPanel 是项滚动 (`ScrollUnit="Item"`)。<br /><br /> 有人呼叫`VirtualizingStackPanel.MakeVisible(v)`滚动元素`v`到视图。 这可在显式或隐式多种方式;可能的最常见方式只需单击`v`以便为其提供键盘焦点。<br /><br /> 在可视化父级链中的从`v`到 VirtualizingStackPanel 经过 TreeViewItem。<br /><br /> 换而言之，出现此消息是 TreeViewItem 使用外部的树视图，并在用户单击 TreeViewItem 以使其视图的后代时。 如果 TreeViewItem 有没有可设定焦点的后代，您将永远不会看到此问题。 命中此时的示例就是情况的时候 TreeViewItem DataTemplate 的根。  当命中此问题时，请没有出现在 WPF 框架引发 InvalidCastException。|  
|建议|修补程序将可为此。|  
|范围|次要|  
|版本|4.5|  
|类型|运行时|  
|分析器|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims 考虑所有但 claimTypes  
  
|||  
|-|-|  
|详细信息|在应用程序面向.NET Framework 4.6.1，如果从在其 SAN 字段中，具有多个 DNS 条目的证书初始化声明集 X509 FindClaims 方法尝试匹配的所有 DNS 条目的 claimType 参数。<br /><br /> 对于面向以前版本的.NET framework 的应用程序，FindClaims 方法尝试匹配的 claimType 参数仅与最后一个 DNS 条目。|  
|建议|此更改仅影响面向.NET Framework 4.6.1 应用程序。 此更改可能被禁用 (或如果启用针对以前&4;.6.1) 与[DisableMultipleDNSEntries](https://msdn.microsoft.com/en-us/library/mt620030%28v=vs.110%29.aspx)兼容性开关。|  
|范围|次要|  
|版本|4.6.1|  
|类型|重定目标|  
|受影响的 Api|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|分析器|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Application.FilterMessage 将不再引发 IMessageFilter.PreFilterMessage 的可重入实现  
  
|||  
|-|-|  
|详细信息|在.NET Framework 4.6.1 中之前, （同时也会调用 Application.DoEvents） 调用的被调用的 AddMessageFilter 或 RemoveMessageFilter 与 IMessageFilter.PreFilterMessage Application.FilterMessage 可能会导致 IndexOutOfRangeException。<br /><br /> 从针对.NET Framework 4.6.1 的应用程序开始，将不再引发此异常，并可重入上文所述可以使用过滤器。|  
|建议|请注意，Application.FilterMessage 将不再引发上面所述的可重入 IMessageFilter.PreFilterMessage 行为。 这只会影响面向.NET Framework 4.6.1 应用程序。<br /><br /> 面向.NET Framework 4.6.1 的应用程序可以退出此更改 （或目标的较旧框架可能会选择在应用程序） 使用[DontSupportReentrantFilterMessage](https://msdn.microsoft.com/en-us/library/mt620032%28v=vs.110%29.aspx)兼容性开关。|  
|范围|边缘|  
|版本|4.6.1|  
|类型|重定目标|  
|受影响的 Api|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|分析器|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture 不会保留在各个 WPF 调度程序操作  
  
|||  
|-|-|  
|详细信息|从.NET Framework 4.6 开始，CurrentCulture CurrentUICulture 更改或内[调度程序](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx)都将丢失该调度程序操作的末尾。 同样，对 CurrentCulture 或 CurrentUICulture 之外的调度程序操作进行的更改可能不会反映在操作执行。<br /><br /> 实际上，这意味着 CurrentCulture 和 CurrentUICulture 更改不可能 WPF UI 回调和 WPF 应用程序中的其他代码之间流动。<br /><br /> 这是因为发生了更改[ExecutionContext](https://msdn.microsoft.com/en-us/library/system.threading.executioncontext%28v=vs.110%29.aspx) ，它使 CurrentCulture 和 CurrentUICulture 将面向.NET Framework 4.6 的应用程序与存储中开始的执行上下文。 WPF 调度程序操作存储用于开始操作和还原以前的上下文，在操作完成时的执行上下文。 CurrentCulture 和 CurrentUICulture 现已成为该上下文的一部分，因为调度程序操作中的对这些更改不会保留在该操作之外。|  
|建议|此更改影响的应用程序可能会通过将存储所需的 CurrentCulture 变通解决它或在字段中的 CurrentUICulture 和签入所有调度程序操作正文 （包括用户界面事件回调处理程序），设置正确的 CurrentCulture 和 CurrentUICulture。 此外，因为 ExecutionContext 更改基础此 WPF 更改仅影响面向.NET Framework 4.6 或更高版本的应用程序 (通过面向.NET Framework 4.5.2，可以避免此换行符）。|  
|范围|次要|  
|版本|4.6|  
|类型|重定目标|  
|分析器|CD0145|