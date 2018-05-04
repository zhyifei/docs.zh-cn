### <a name="aspnet-accessibility-improvement-in-net-471"></a>.NET 4.7.1 中的 ASP.NET 辅助功能改进

|   |   |
|---|---|
|详细信息|ASP.NET 将改进 ASP.NET Web 控件与 Visual Studio 中辅助功能技术配合使用的方式，以便更好地为 ASP.NET 客户提供支持。  其中包括以下更改：<ul><li>在控件中实现缺失 UI 的辅助功能模式，如“详细信息视图”向导中的“添加字段”对话框。</li><li>改善在高对比度模式下（如数据页导航字段编辑器）的显示。</li><li>改善控件（如配置对象上下文窗口或配置数据源窗口）的键盘导航体验。</li></ul>|
|建议|**如何选择启用或弃用这些更改** 为使 Visual Studio 设计器从这些更改中获益，它必须在 .NET Framework 4.7.1 或更高版本上运行。 Web 应用程序可通过以下任何一种方式从这些更改中获益：<ul><li>安装 Visual Studio 2017 15.3 或更高版本，它在默认情况下使用以下 AppContext 开关支持新的辅助功能。</li><li>如以下示例所示，通过将“Switch.UseLegacyAccessibility”AppContext 开关添加到 devenv.exe.config 文件中的 `<runtime>` 部分并将其设置为 `false`，可选择弃用旧版辅助功能行为。</li></ul><pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;<br />&lt;configuration&gt;<br />&lt;runtime&gt;<br />...</code></pre>|
|范围|次要|
|版本|4.7.1|
|类型|重定目标|
