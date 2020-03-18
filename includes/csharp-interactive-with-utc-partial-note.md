---
ms.openlocfilehash: 814372535f5c7a91f1df250404018228e4c4c812
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "73198367"
---

> [!NOTE]
> <span data-ttu-id="d6894-101">本文中的一些 C# 示例在 [Try.NET](https://dotnet.microsoft.com/platform/try-dotnet) 内联代码运行程序和演练环境中运行。</span><span class="sxs-lookup"><span data-stu-id="d6894-101">Some of the C# examples in this article run in the [Try.NET](https://dotnet.microsoft.com/platform/try-dotnet) inline code runner and playground.</span></span> <span data-ttu-id="d6894-102">选择“运行”按钮以在交互窗口中运行示例  。</span><span class="sxs-lookup"><span data-stu-id="d6894-102">Select the **Run** button to run an example in an interactive window.</span></span> <span data-ttu-id="d6894-103">执行代码后，可通过再次选择“运行”来修改它并运行已修改的代码  。</span><span class="sxs-lookup"><span data-stu-id="d6894-103">Once you execute the code, you can modify it and run the modified code by selecting **Run** again.</span></span> <span data-ttu-id="d6894-104">已修改的代码要么在交互窗口中运行，要么编译失败时，交互窗口将显示所有 C# 编译器错误消息。</span><span class="sxs-lookup"><span data-stu-id="d6894-104">The modified code either runs in the interactive window or, if compilation fails, the interactive window displays all C# compiler error messages.</span></span>
>
> <span data-ttu-id="d6894-105">[Try.NET](xref:System.TimeZoneInfo.Local) 内联代码运行程序和演练环境的[本地时区](https://dotnet.microsoft.com/platform/try-dotnet)是协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="d6894-105">The [local time zone](xref:System.TimeZoneInfo.Local) of the [Try.NET](https://dotnet.microsoft.com/platform/try-dotnet) inline code runner and playground is Coordinated Universal Time, or UTC.</span></span> <span data-ttu-id="d6894-106">这可能会影响用于说明 <xref:System.DateTime>、<xref:System.DateTimeOffset> 和 <xref:System.TimeZoneInfo> 类型及其成员的示例的行为和输出。</span><span class="sxs-lookup"><span data-stu-id="d6894-106">This may affect the behavior and the output of examples that illustrate the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types and their members.</span></span>
