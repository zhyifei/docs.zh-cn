---
title: "入门 (WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started [WPF]
- introduction [WPF]
- WPF [WPF], getting started
ms.assetid: 04f91da8-708c-46c7-8172-f1695ec847cd
caps.latest.revision: "60"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b74eafb1189335a642df7cb267727ef7e8ee59b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-wpf"></a><span data-ttu-id="fa3d1-102">入门 (WPF)</span><span class="sxs-lookup"><span data-stu-id="fa3d1-102">Getting Started (WPF)</span></span>
<span data-ttu-id="fa3d1-103">Windows Presentation Foundation (WPF) 是一个可创建桌面客户端应用程序的 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="fa3d1-103">Windows Presentation Foundation (WPF) is a UI framework that creates desktop client applications.</span></span> <span data-ttu-id="fa3d1-104">WPF 开发平台支持广泛的应用程序开发功能，包括应用程序模型、资源、控件、图形、布局、数据绑定、文档和安全性。</span><span class="sxs-lookup"><span data-stu-id="fa3d1-104">The WPF development platform supports a broad set of application development features, including an application model, resources, controls, graphics, layout, data binding, documents, and security.</span></span> <span data-ttu-id="fa3d1-105">它是 .NET Framework 的子集，因此，如果你曾经使用 ASP.NET 或 Windows 窗体通过 .NET Framework 构建应用程序，应该会熟悉此编程体验。</span><span class="sxs-lookup"><span data-stu-id="fa3d1-105">It is a subset of the .NET Framework, so if you have previously built applications with the .NET Framework using ASP.NET or Windows Forms, the programming experience should be familiar.</span></span> <span data-ttu-id="fa3d1-106">WPF 使用可扩展应用程序标记语言 (XAML) 为应用程序编程提供声明性模型。</span><span class="sxs-lookup"><span data-stu-id="fa3d1-106">WPF uses the Extensible Application Markup Language (XAML) to provide a declarative model for application programming.</span></span> <span data-ttu-id="fa3d1-107">本节包含 WPF 简介及入门帮助等主题。</span><span class="sxs-lookup"><span data-stu-id="fa3d1-107">This section has topics that introduce and help you get started with WPF.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="fa3d1-108">从何处开始？</span><span class="sxs-lookup"><span data-stu-id="fa3d1-108">Where Should I Start?</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa3d1-109">我希望直接开始使用…</span><span class="sxs-lookup"><span data-stu-id="fa3d1-109">I want to jump right in…</span></span>|[<span data-ttu-id="fa3d1-110">演练：我的第一个 WPF 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="fa3d1-110">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|  
|<span data-ttu-id="fa3d1-111">如何设计应用程序 UI？</span><span class="sxs-lookup"><span data-stu-id="fa3d1-111">How do I design the application UI?</span></span>|[<span data-ttu-id="fa3d1-112">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="fa3d1-112">Designing XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)|  
|<span data-ttu-id="fa3d1-113">是否是初次使用 .NET？</span><span class="sxs-lookup"><span data-stu-id="fa3d1-113">New to .NET?</span></span>|<span data-ttu-id="fa3d1-114">[.NET Framework 概述](https://msdn.microsoft.com/en-us/library/zw4w595w\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fa3d1-114">[Overview of the .NET Framework](https://msdn.microsoft.com/en-us/library/zw4w595w\(v=vs.140\).aspx)</span></span><br /><br /> [<span data-ttu-id="fa3d1-115">.NET Framework 应用程序要点</span><span class="sxs-lookup"><span data-stu-id="fa3d1-115">.NET Framework Application Essentials</span></span>](../../../../docs/standard/application-essentials.md)<br /><br /> <span data-ttu-id="fa3d1-116">[Visual C# 和 Visual Basic 入门](https://msdn.microsoft.com/en-us/library/dd492171\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fa3d1-116">[Getting Started with Visual C# and Visual Basic](https://msdn.microsoft.com/en-us/library/dd492171\(v=vs.140\).aspx)</span></span>|  
|<span data-ttu-id="fa3d1-117">有关 WPF 的详细信息...</span><span class="sxs-lookup"><span data-stu-id="fa3d1-117">Tell me more about WPF…</span></span>|[<span data-ttu-id="fa3d1-118">Visual Studio 2015 中的 WPF 简介</span><span class="sxs-lookup"><span data-stu-id="fa3d1-118">Introduction to WPF in Visual Studio 2015</span></span>](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)<br /><br /> [<span data-ttu-id="fa3d1-119">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="fa3d1-119">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)<br /><br /> [<span data-ttu-id="fa3d1-120">控件</span><span class="sxs-lookup"><span data-stu-id="fa3d1-120">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)<br /><br /> [<span data-ttu-id="fa3d1-121">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="fa3d1-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)|  
|<span data-ttu-id="fa3d1-122">是否是 Windows 窗体开发人员？</span><span class="sxs-lookup"><span data-stu-id="fa3d1-122">Are you a Windows Forms developer?</span></span>|[<span data-ttu-id="fa3d1-123">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="fa3d1-123">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)<br /><br /> [<span data-ttu-id="fa3d1-124">WPF 和 Windows 窗体互操作</span><span class="sxs-lookup"><span data-stu-id="fa3d1-124">WPF and Windows Forms Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)|  
  
## <a name="see-also"></a><span data-ttu-id="fa3d1-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa3d1-125">See Also</span></span>  
 [<span data-ttu-id="fa3d1-126">类库</span><span class="sxs-lookup"><span data-stu-id="fa3d1-126">Class Library</span></span>](../../../../docs/framework/wpf/class-library-wpf.md)  
 [<span data-ttu-id="fa3d1-127">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="fa3d1-127">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
 [<span data-ttu-id="fa3d1-128">.NET framework 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="fa3d1-128">.NET Framework Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=187437)
