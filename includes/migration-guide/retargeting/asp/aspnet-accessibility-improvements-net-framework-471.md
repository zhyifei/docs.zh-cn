### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a>.NET Framework 4.7.1 中的 ASP.NET 辅助功能改进

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.7.1 开始，ASP.NET 改进了 ASP.NET Web 控件与 Visual Studio 中的辅助功能技术配合使用的方式，以更好地支持 ASP.NET 客户。  其中包括以下更改：<ul><li>在以下控件中实现缺失 UI 的辅助功能模式：例如“详细信息视图”向导中的“添加字段”对话框或“ListView”向导的“配置 ListView”对话框。</li><li>改善在高对比度模式下（如数据页导航字段编辑器）的显示。</li><li>改善以下控件的键盘导航体验：例如 DataPager 控件的“编辑页导航字段”向导中的“字段”对话框、“配置 ObjectContext”对话框或“配置数据源”向导的“配置数据选择”对话框。</li></ul>|
|建议|<strong>如何选择启用或选择弃用这些更改</strong>为使 Visual Studio 设计器从这些更改获益，它必须在 .NET Framework 4.7.1 或更高版本上运行。 Web 应用程序可通过以下任何一种方式从这些更改中获益：<ul><li>安装 Visual Studio 2017 15.3 或更高版本，它在默认情况下使用以下 AppContext 开关支持新的辅助功能。</li><li>如以下示例所示，通过将 <code>Switch.UseLegacyAccessibilityFeatures</code> AppContext 开关添加到 devenv.exe.config 文件中的 <code>&lt;runtime&gt;</code> 部分并将其设置为 <code>false</code>，可选择弃用旧版辅助功能行为。</li></ul><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;...&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false&#39;  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;...&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>面向 .NET Framework 4.7.1 或更高版本并希望保留旧版辅助功能行为的应用程序，可通过将此 AppContext 开关显式设置为 <code>true</code> 来选择启用旧版辅助功能。|
|范围|次要|
|版本|4.7.1|
|类型|重定目标|

