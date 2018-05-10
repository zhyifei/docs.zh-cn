### <a name="changes-in-path-normalization"></a>路径规范化中的更改

|   |   |
|---|---|
|详细信息|从面向 .NET Framework 4.6.2 的应用开始，运行时规范路径的方式发生了变化。路径规范化涉及修改用于标识路径或文件的字符串，使其与目标操作系统上的有效路径一致。 路径规范化通常涉及以下操作：<ul><li>规范化处理组件和目录分隔符。</li><li>将当前目录应用到相对路径。</li><li>评估路径中的相对目录 (.) 或父目录 (..)。</li><li>删减指定字符。</li></ul>从面向 .NET Framework 4.6.2 的应用开始，在路径规范化中默认启用以下更改：<ul><li>运行时在规范化处理路径时以操作系统的 [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963(v=vs.85).aspx) 函数为准。</li><li>路径规范化再也不用删减目录部分的末尾内容（如目录名称末尾的空格）。</li><li>支持完全信任的设备路径语法，包括 <code>\.&lt;/code&gt; and, for file I/O APIs in mscorlib.dll, <code>\?&lt;/code&gt;.</li><li>The runtime does not validate device syntax paths.</li><li>The use of device syntax to access alternate data streams is supported.</li></ul>These changes improve performance while allowing methods to access previously inaccessible paths. Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.|
|建议|对于面向 .NET Framework 4.6.2 或更高版本的应用，可通过将以下内容添加到应用程序配置文件的 <code>&lt;runtime&gt;</code> 部分，选择弃用此更改而使用旧版规范化：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>对于面向 .NET Framework 4.6.1 及更低版本，但在 .NET Framework 4.6.2 或更高版本上运行的应用，可通过将以下行添加到应用程序配置文件的 <code>&lt;runtime&gt;</code> 部分，启用对路径规范化的更改：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.6.2|
|类型|重定目标|

