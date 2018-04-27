### <a name="incorrect-implementation-of-memberdescriptorequals"></a>MemberDescriptor.Equals 实现不正确

|   |   |
|---|---|
|详细信息|“Equals”方法的原始实现是通过比较类别名称和描述字符串来比较对象的两个不同字符串属性。 解决方法是将第一个对象和第二个对象的“类别”进行比较，然后再比较“描述”。 如果面向 4.6.2，则可以将 MemberDescriptorEqualsReturnsFalseIfEquivalent 配置值设为 true 以选择弃用新行为；如果面向低于 4.6.2 的框架版本，则设为 false 启用此修复。|
|建议|描述符相等时如果应用程序依赖于有时返回 false 的 MemberDescriptor.Equals 并且面向 .NET Framework 4.6.2 版，那么你可以采用以下几个选项：<ol><li>除运行 Equals 方法外，更改代码以手动比较“类别”和“描述”字段。</li><li>将以下值添加到 app.config 文件从而选择弃用此更改：</li></ol><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>如果应用程序面向 4.6.1 或更低版本的 .NET Framework 并且想要启用此更改，可以通过将以下值添加到 app.config 文件，将兼容性开关设为 false：<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|边缘|
|版本|4.6.2|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|

