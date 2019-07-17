---
ms.openlocfilehash: 9c54572b8dcedaa103db8503cfc1155b4698c3ed
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803437"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>符号的工作流 XAML 校验和从 SHA1 更改为 SHA256

|   |   |
|---|---|
|详细信息|为支持使用 Visual Studio 进行调试，工作流运行时使用哈希算法生成工作流 XAML 文件的校验和。 在 .NET Framework 4.6.2 和早期版本中，工作流校验和哈希使用 MD5 算法，这会在启用 FIPS 的系统上导致问题。 从 .NET Framework 4.7 开始，默认算法已更改为 SHA1。 从 .NET Framework 4.8 开始，默认算法已更改为 SHA256。|
|建议|如果由于校验和失败，代码无法加载工作流实例或找不到相应符号，请尝试将 <code>AppContext</code> 开关 &quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; 设置为 true。在代码中：<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot;, true);&#13;&#10;</code></pre>或在配置中：<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|范围|次要|
|Version|4.8|
|类型|重定目标|

