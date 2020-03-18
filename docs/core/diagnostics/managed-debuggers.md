---
title: 托管调试器 - .NET Core
description: Visual Studio 和 Visual Studio Code 托管调试器的概述。
ms.date: 08/05/2019
ms.openlocfilehash: 065b1b0fc32eb76b398cb3821c8592a1955c9359
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715558"
---
# <a name="net-core-managed-debuggers"></a><span data-ttu-id="fdefe-103">.NET Core 托管调试器</span><span class="sxs-lookup"><span data-stu-id="fdefe-103">.NET Core managed debuggers</span></span>

<span data-ttu-id="fdefe-104">调试器允许逐步骤暂停或执行程序。</span><span class="sxs-lookup"><span data-stu-id="fdefe-104">Debuggers allow programs to be paused or executed step-by-step.</span></span> <span data-ttu-id="fdefe-105">暂停后，可以查看进程的当前状态。</span><span class="sxs-lookup"><span data-stu-id="fdefe-105">When paused, the current state of the process can be viewed.</span></span> <span data-ttu-id="fdefe-106">通过逐步完成关键部分，你可以了解代码以及产生这一结果的原因。</span><span class="sxs-lookup"><span data-stu-id="fdefe-106">By stepping through key sections, you gain understanding of your code and why it produces the result that it does.</span></span>

<span data-ttu-id="fdefe-107">Microsoft 在  Visual Studio 和  Visual Studio Code 中提供托管代码的调试器。</span><span class="sxs-lookup"><span data-stu-id="fdefe-107">Microsoft provides debuggers for managed code in **Visual Studio** and **Visual Studio Code**.</span></span>

## <a name="visual-studio-managed-debugger"></a><span data-ttu-id="fdefe-108">Visual Studio 托管调试器</span><span class="sxs-lookup"><span data-stu-id="fdefe-108">Visual Studio managed debugger</span></span>

<span data-ttu-id="fdefe-109"> Visual Studio 是一个集成开发环境，其中提供了最全面的调试器。</span><span class="sxs-lookup"><span data-stu-id="fdefe-109">**Visual Studio** is an integrated development environment with the most comprehensive debugger available.</span></span> <span data-ttu-id="fdefe-110">Visual Studio 是 Windows 开发人员的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="fdefe-110">Visual Studio is an excellent choice for developers working on Windows.</span></span>

- [<span data-ttu-id="fdefe-111">教程 - 使用 Visual Studio 在 Windows 上调试 .NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="fdefe-111">Tutorial - Debugging a .NET Core application on Windows with Visual Studio</span></span>](../tutorials/debugging-with-visual-studio.md)

<span data-ttu-id="fdefe-112">尽管 Visual Studio 是一个 Windows 应用程序，但仍可用于远程调试 Linux 和 macOS 应用。</span><span class="sxs-lookup"><span data-stu-id="fdefe-112">While Visual Studio is a Windows application, it can still be used to debug Linux and macOS apps remotely.</span></span>

- [<span data-ttu-id="fdefe-113">使用 Visual Studio 在 Linux/OSX 上调试 .NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="fdefe-113">Debugging a .NET Core application on Linux/OSX with Visual Studio</span></span>](https://github.com/Microsoft/MIEngine/wiki/Offroad-Debugging-of-.NET-Core-on-Linux---OSX-from-Visual-Studio)

 <span data-ttu-id="fdefe-114">调试 ASP.NET Core 应用需要略微不同的说明。</span><span class="sxs-lookup"><span data-stu-id="fdefe-114">Debugging ASP.NET Core apps require slightly different instructions.</span></span>

- [<span data-ttu-id="fdefe-115">在 Visual Studio 中调试 ASP.NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="fdefe-115">Debug ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications#debug-aspnet-core-apps)

## <a name="visual-studio-code-managed-debugger"></a><span data-ttu-id="fdefe-116">Visual Studio Code 托管调试器</span><span class="sxs-lookup"><span data-stu-id="fdefe-116">Visual Studio Code managed debugger</span></span>

<span data-ttu-id="fdefe-117"> Visual Studio Code 是轻量型跨平台代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="fdefe-117">**Visual Studio Code** is a lightweight cross-platform code editor.</span></span> <span data-ttu-id="fdefe-118">它使用与 Visual Studio 相同的 .NET Core 调试器实现，但使用的是简化的用户界面。</span><span class="sxs-lookup"><span data-stu-id="fdefe-118">It uses the same .NET Core debugger implementation as Visual Studio, but with a simplified user interface.</span></span>

- [<span data-ttu-id="fdefe-119">教程 - 使用 Visual Studio Code 调试 .NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="fdefe-119">Tutorial - Debugging a .NET Core application with Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md#debug)
- [<span data-ttu-id="fdefe-120">在 Visual Studio Code 中进行调试</span><span class="sxs-lookup"><span data-stu-id="fdefe-120">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)
