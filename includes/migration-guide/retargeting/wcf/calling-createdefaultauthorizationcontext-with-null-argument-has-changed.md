---
ms.openlocfilehash: 9ec5fa379556dedeaa7a35e34f004340ab47a39c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234344"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>调用具有 null 自变量的 CreateDefaultAuthorizationContext 的方式已更改

|   |   |
|---|---|
|详细信息|调用具有 null authorizationPolicies 自变量的 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=name> 所返回的 <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=name> 实现更改了其在 .NET Framework 4.6 中的实现。|
|建议|在极少数情况下，使用自定义身份验证的 WCF 应用可能会看到行为差异。 在这类情况下，可使用以下两种方式之一还原以前的行为：<ol><li>重新编译你的应用以面向早于 4.6 的 .NET Framework 版本。 对于 IIS 承载的服务，请使用 &lt;httpRuntime targetFramework=x.x /&gt; 元素以面向早期版本的 .NET Framework&quot;&quot;。</li><li>将下面的行添加到 app.config 文件的 <code>&lt;appSettings&gt;</code> 部分： <code>&lt;add key=&quot;appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext&quot; value=&quot;true&quot; /&gt;</code></li></ol>|
|范围|次要|
|版本|4.6|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType></li></ul>|
