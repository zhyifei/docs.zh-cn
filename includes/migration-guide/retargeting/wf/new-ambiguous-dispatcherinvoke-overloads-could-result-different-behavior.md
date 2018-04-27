### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>新的（不明确的）Dispatcher.Invoke 重载可能导致不同的行为

|   |   |
|---|---|
|详细信息|.NET Framework 4.5 将新重载添加到包括 <xref:System.Action> 类型参数的 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType>。 在重新编译现有代码时，编译器可能将对具有 <xref:System.Delegate> 参数的 Dispatcher.Invoke 方法的调用解析为对具有 <xref:System.Action> 参数的 Dispatcher.Invoke 方法的调用。 如果将对具有 <xref:System.Delegate> 参数的 Dispatcher.Invoke 重载的调用解析为对具有 <xref:System.Action> 参数的 Dispatcher.Invoke 重载的调用，可能出现以下行为差异：<ul><li>如果出现异常，则不引发 <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> 和 <xref:System.Windows.Threading.Dispatcher.UnhandledException> 事件。 相反，通过 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=name> 事件处理异常。</li><li>对某些成员（如 <xref:System.Windows.Threading.DispatcherOperation.Result>）的调用会受阻，直到操作完成。</li></ul>|
|建议|若要避免出现多义性（以及异常处理或阻止行为中可能出现的差异），调用 Dispatcher.Invoke 的代码可传递空 object[] 作为 Invoke 调用的第二个参数，确保解析为 .NET 4.0 方法重载。|
|范围|次要|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType></li></ul>|

