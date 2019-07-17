---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802714"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="bdddf-101">.NET COM 成功封送事件上的 ByRef SafeArray 参数</span><span class="sxs-lookup"><span data-stu-id="bdddf-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bdddf-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="bdddf-102">Details</span></span>|<span data-ttu-id="bdddf-103">在 .NET Framework 4.7.2 及更低版本中，COM 事件上的 ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) 参数无法封送回本机代码。</span><span class="sxs-lookup"><span data-stu-id="bdddf-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="bdddf-104">进行此更改后，[SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) 现在可成功进行封送。</span><span class="sxs-lookup"><span data-stu-id="bdddf-104">With this change the [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="bdddf-105">[x] Quirked</span><span class="sxs-lookup"><span data-stu-id="bdddf-105">[ x ] Quirked</span></span></li></ul>|
|<span data-ttu-id="bdddf-106">建议</span><span class="sxs-lookup"><span data-stu-id="bdddf-106">Suggestion</span></span>|<span data-ttu-id="bdddf-107">如果正确封送 COM 事件上的 ByRef SafeArray 参数会中断执行，则可以通过将以下配置开关添加到应用程序配置来禁用此代码：</span><span class="sxs-lookup"><span data-stu-id="bdddf-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="bdddf-108">范围</span><span class="sxs-lookup"><span data-stu-id="bdddf-108">Scope</span></span>|<span data-ttu-id="bdddf-109">次要</span><span class="sxs-lookup"><span data-stu-id="bdddf-109">Minor</span></span>|
|<span data-ttu-id="bdddf-110">Version</span><span class="sxs-lookup"><span data-stu-id="bdddf-110">Version</span></span>|<span data-ttu-id="bdddf-111">4.8</span><span class="sxs-lookup"><span data-stu-id="bdddf-111">4.8</span></span>|
|<span data-ttu-id="bdddf-112">类型</span><span class="sxs-lookup"><span data-stu-id="bdddf-112">Type</span></span>|<span data-ttu-id="bdddf-113">运行时</span><span class="sxs-lookup"><span data-stu-id="bdddf-113">Runtime</span></span>|

