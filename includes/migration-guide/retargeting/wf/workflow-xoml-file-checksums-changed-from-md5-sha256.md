---
ms.openlocfilehash: c44971dfd65ee31657279daec2d34b8cfa8d4860
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410405"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a>工作流 XOML 文件校验和已从 MD5 更改为 SHA256

|   |   |
|---|---|
|详细信息|为了支持使用 Visual Studio 调试基于 XOML 的工作流，当生成包含 XOML 文件的工作流项目时，系统会将 XOML 文件内容的校验和作为 <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType> 值包含在生成的代码中。 在 .NET Framework 4.7.2 和早期版本中，该校验和哈希使用 MD5 算法，这会在启用 FIPS 的系统上导致问题。 从 .NET Framework 4.8 开始，采用的算法为 SHA256。 为了与 WorkflowMarkupSourceAttribute.MD5Digest 兼容，只使用生成的校验和的前 16 个字节。这可能会导致调试过程中出现问题。 可能需要重新生成项目。|
|建议|如果重新生成项目没有解决问题，请尝试在代码中将 <code>AppContext</code> 开关 &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; 设置为 true：<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>或者在配置文件中设置（需要位于正在使用的 MSBuild.exe 的 MSBuild.exe.config 中）：<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|范围|次要|
|Version|4.8|
|类型|重定目标|
