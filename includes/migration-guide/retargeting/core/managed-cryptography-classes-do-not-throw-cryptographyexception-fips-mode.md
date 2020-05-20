---
ms.openlocfilehash: f1f37e61917e8331b06d91e6abebfe4ce3288e7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "69564334"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a>托管加密类不会在 FIPS 模式下引发 CryptographyException

|   |   |
|---|---|
|详细信息|在 .NET framework 4.7.2 及更低版本中，当在 FIPS 模式下配置系统加密库时，<xref:System.Security.Cryptography.SHA256Managed> 等托管加密提供程序类会引发 <xref:System.Security.Cryptography.CryptographicException>。 引发这些异常的原因是托管版本未经过 FIPS（联邦信息处理标准）140-2 认证，以及没有阻止根据 FIPS 规则规定未被认可的加密算法。  由于很少有开发人员将其开发计算机置于 FIPS 模式下，因此这些异常通常仅在生产系统上引发。面向 .NET Framework 4.8 及更高版本的应用程序会自动切换到新的且宽松的策略，以便在这种情况下默认不再引发 <xref:System.Security.Cryptography.CryptographicException>。 相反，托管加密类会将加密操作重定向到系统加密库。 此系统更改可有效地删除开发人员环境和生产环境之间可能令人混淆的差异，并使本机组件和托管组件采用相同的加密策略运行。|
|建议|如果不希望出现这种情况，可以选择退出该行为并还原上述行为，方法是将以下 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 配置设置添加到应用程序配置文件的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中，以便在 FIPS 模式下引发 <xref:System.Security.Cryptography.CryptographicException>：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.UseLegacyFipsThrow=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>如果应用程序面向 .NET Framework 4.7.2 或更低版本，则也可以通过将以下 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 配置设置添加到应用程序配置文件的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分来选择加入此更改：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.UseLegacyFipsThrow=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|边缘|
|Version|4.8|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType></li></ul>|
