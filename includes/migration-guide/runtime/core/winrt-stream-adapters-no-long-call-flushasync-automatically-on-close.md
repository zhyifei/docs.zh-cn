---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803376"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="73e15-101">WinRT 流适配器不再在关闭时自动调用 FlushAsync</span><span class="sxs-lookup"><span data-stu-id="73e15-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

|   |   |
|---|---|
|<span data-ttu-id="73e15-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="73e15-102">Details</span></span>|<span data-ttu-id="73e15-103">在 Windows 应用商店的应用中，Windows 运行时流适配器不再从 Dispose 方法调用 FlushAsync 方法。</span><span class="sxs-lookup"><span data-stu-id="73e15-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>|
|<span data-ttu-id="73e15-104">建议</span><span class="sxs-lookup"><span data-stu-id="73e15-104">Suggestion</span></span>|<span data-ttu-id="73e15-105">此更改应该为透明。</span><span class="sxs-lookup"><span data-stu-id="73e15-105">This change should be transparent.</span></span> <span data-ttu-id="73e15-106">开发人员可以通过编写如下代码还原之前的行为：</span><span class="sxs-lookup"><span data-stu-id="73e15-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="73e15-107">范围</span><span class="sxs-lookup"><span data-stu-id="73e15-107">Scope</span></span>|<span data-ttu-id="73e15-108">透明</span><span class="sxs-lookup"><span data-stu-id="73e15-108">Transparent</span></span>|
|<span data-ttu-id="73e15-109">Version</span><span class="sxs-lookup"><span data-stu-id="73e15-109">Version</span></span>|<span data-ttu-id="73e15-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="73e15-110">4.5.1</span></span>|
|<span data-ttu-id="73e15-111">类型</span><span class="sxs-lookup"><span data-stu-id="73e15-111">Type</span></span>|<span data-ttu-id="73e15-112">运行时</span><span class="sxs-lookup"><span data-stu-id="73e15-112">Runtime</span></span>|
