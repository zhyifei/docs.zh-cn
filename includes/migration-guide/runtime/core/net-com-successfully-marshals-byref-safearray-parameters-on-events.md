---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802714"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM 成功封送事件上的 ByRef SafeArray 参数

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.7.2 及更低版本中，COM 事件上的 ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) 参数无法封送回本机代码。  进行此更改后，[SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) 现在可成功进行封送。<ul><li>[x] Quirked</li></ul>|
|建议|如果正确封送 COM 事件上的 ByRef SafeArray 参数会中断执行，则可以通过将以下配置开关添加到应用程序配置来禁用此代码：<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|范围|次要|
|Version|4.8|
|类型|运行时|

