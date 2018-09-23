---
title: 入门 (WPF)
ms.date: 01/26/2018
helpviewer_keywords:
- getting started [WPF]
- introduction [WPF]
- WPF [WPF], getting started
ms.assetid: 04f91da8-708c-46c7-8172-f1695ec847cd
ms.openlocfilehash: f4c4c4a19c1919a27c15c623bcb30a119a560c75
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2018
ms.locfileid: "46702863"
---
# <a name="getting-started-wpf"></a><span data-ttu-id="0df99-102">入门 (WPF)</span><span class="sxs-lookup"><span data-stu-id="0df99-102">Getting Started (WPF)</span></span>
<span data-ttu-id="0df99-103">Windows Presentation Foundation (WPF) 是一个可创建桌面客户端应用程序的 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="0df99-103">Windows Presentation Foundation (WPF) is a UI framework that creates desktop client applications.</span></span> <span data-ttu-id="0df99-104">WPF 开发平台支持广泛的应用程序开发功能，包括应用程序模型、资源、控件、图形、布局、数据绑定、文档和安全性。</span><span class="sxs-lookup"><span data-stu-id="0df99-104">The WPF development platform supports a broad set of application development features, including an application model, resources, controls, graphics, layout, data binding, documents, and security.</span></span> <span data-ttu-id="0df99-105">它是 .NET Framework 的子集，因此，如果你曾经使用 ASP.NET 或 Windows 窗体通过 .NET Framework 构建应用程序，应该会熟悉此编程体验。</span><span class="sxs-lookup"><span data-stu-id="0df99-105">It is a subset of the .NET Framework, so if you have previously built applications with the .NET Framework using ASP.NET or Windows Forms, the programming experience should be familiar.</span></span> <span data-ttu-id="0df99-106">WPF 使用可扩展应用程序标记语言 (XAML) 为应用程序编程提供声明性模型。</span><span class="sxs-lookup"><span data-stu-id="0df99-106">WPF uses the Extensible Application Markup Language (XAML) to provide a declarative model for application programming.</span></span> <span data-ttu-id="0df99-107">本节包含 WPF 简介及入门帮助等主题。</span><span class="sxs-lookup"><span data-stu-id="0df99-107">This section has topics that introduce and help you get started with WPF.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="0df99-108">从何处开始？</span><span class="sxs-lookup"><span data-stu-id="0df99-108">Where Should I Start?</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0df99-109">我希望直接开始使用…</span><span class="sxs-lookup"><span data-stu-id="0df99-109">I want to jump right in…</span></span>|[<span data-ttu-id="0df99-110">演练：我的第一个 WPF 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="0df99-110">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|  
|<span data-ttu-id="0df99-111">如何设计应用程序 UI？</span><span class="sxs-lookup"><span data-stu-id="0df99-111">How do I design the application UI?</span></span>|[<span data-ttu-id="0df99-112">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="0df99-112">Designing XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)|  
|<span data-ttu-id="0df99-113">是否是初次使用 .NET？</span><span class="sxs-lookup"><span data-stu-id="0df99-113">New to .NET?</span></span>|<span data-ttu-id="0df99-114">[.NET Framework 概述](https://msdn.microsoft.com/library/zw4w595w\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0df99-114">[Overview of the .NET Framework](https://msdn.microsoft.com/library/zw4w595w\(v=vs.140\).aspx)</span></span><br /><br /> [<span data-ttu-id="0df99-115">.NET Framework 应用程序要点</span><span class="sxs-lookup"><span data-stu-id="0df99-115">.NET Framework Application Essentials</span></span>](../../../../docs/standard/application-essentials.md)<br /><br /> [<span data-ttu-id="0df99-116">Visual C# 和 Visual Basic 入门</span><span class="sxs-lookup"><span data-stu-id="0df99-116">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)|  
|<span data-ttu-id="0df99-117">有关 WPF 的详细信息...</span><span class="sxs-lookup"><span data-stu-id="0df99-117">Tell me more about WPF…</span></span>|[<span data-ttu-id="0df99-118">Visual Studio 中的 WPF 简介</span><span class="sxs-lookup"><span data-stu-id="0df99-118">Introduction to WPF in Visual Studio</span></span>](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)<br /><br /> [<span data-ttu-id="0df99-119">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="0df99-119">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)<br /><br /> [<span data-ttu-id="0df99-120">控件</span><span class="sxs-lookup"><span data-stu-id="0df99-120">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)<br /><br /> [<span data-ttu-id="0df99-121">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="0df99-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)|  
|<span data-ttu-id="0df99-122">是否是 Windows 窗体开发人员？</span><span class="sxs-lookup"><span data-stu-id="0df99-122">Are you a Windows Forms developer?</span></span>|[<span data-ttu-id="0df99-123">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="0df99-123">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)<br /><br /> [<span data-ttu-id="0df99-124">WPF 和 Windows 窗体互操作</span><span class="sxs-lookup"><span data-stu-id="0df99-124">WPF and Windows Forms Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)|  
  
## <a name="see-also"></a><span data-ttu-id="0df99-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0df99-125">See Also</span></span>  
 [<span data-ttu-id="0df99-126">类库</span><span class="sxs-lookup"><span data-stu-id="0df99-126">Class Library</span></span>](../../../../docs/framework/wpf/class-library-wpf.md)  
 [<span data-ttu-id="0df99-127">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="0df99-127">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
 [<span data-ttu-id="0df99-128">.NET framework 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="0df99-128">.NET Framework Developer Center</span></span>](https://www.microsoft.com/net)
