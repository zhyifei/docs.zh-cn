---
title: 使用 .NET Core 3.1 在 Windows 10 上对桌面应用进行现代化改造
description: 了解如何使用 .NET Core 3.1 对现有桌面应用进行现代化改造
ms.date: 05/12/2020
ms.openlocfilehash: 5861f806a9158ef761c47bc23e51327d4e2d0480
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83422661"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-core-31"></a><span data-ttu-id="95b1b-103">使用 .NET Core 3.1 在 Windows 10 上对桌面应用进行现代化改造</span><span class="sxs-lookup"><span data-stu-id="95b1b-103">Modernizing Desktop Apps on Windows 10 with .NET Core 3.1</span></span>

![显示“对桌面应用进行现代化改造”电子书封面的屏幕截图。](./media/modernizing-existing-desktop-apps-ebook-cover.png)

<span data-ttu-id="95b1b-105">发布者</span><span class="sxs-lookup"><span data-stu-id="95b1b-105">PUBLISHED BY</span></span>

<span data-ttu-id="95b1b-106">Microsoft 开发人员部门、.NET 和 Visual Studio 产品团队</span><span class="sxs-lookup"><span data-stu-id="95b1b-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="95b1b-107">Microsoft Corporation 的一个部门</span><span class="sxs-lookup"><span data-stu-id="95b1b-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="95b1b-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="95b1b-108">One Microsoft Way</span></span>

<span data-ttu-id="95b1b-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="95b1b-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="95b1b-110">版权所有 © 2020 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="95b1b-110">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="95b1b-111">保留所有权利。</span><span class="sxs-lookup"><span data-stu-id="95b1b-111">All rights reserved.</span></span> <span data-ttu-id="95b1b-112">未经发布者书面许可，不得以任何形式或任何方式复制或传播本书中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="95b1b-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="95b1b-113">本书“按原样”提供，表达作者的观点和看法。</span><span class="sxs-lookup"><span data-stu-id="95b1b-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="95b1b-114">本书中表达的观点、看法和信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="95b1b-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="95b1b-115">本书中提及的一些示例仅用于说明，纯属虚构。</span><span class="sxs-lookup"><span data-stu-id="95b1b-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="95b1b-116">不存在任何实际关联或联系，请勿妄加推断。</span><span class="sxs-lookup"><span data-stu-id="95b1b-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="95b1b-117">Microsoft 和 <https://www.microsoft.com> 上“商标”网页列出的商标是 Microsoft 集团公司的商标。</span><span class="sxs-lookup"><span data-stu-id="95b1b-117">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="95b1b-118">Mac 和 macOS 是 Apple Inc. 的商标</span><span class="sxs-lookup"><span data-stu-id="95b1b-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="95b1b-119">所有其他标记和徽标均为其各自所有者的财产。</span><span class="sxs-lookup"><span data-stu-id="95b1b-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="95b1b-120">合著者：</span><span class="sxs-lookup"><span data-stu-id="95b1b-120">Co-Authors:</span></span>

> <span data-ttu-id="95b1b-121">Microsoft .NET 团队项目经理 Olia Gavrysh </span><span class="sxs-lookup"><span data-stu-id="95b1b-121">**Olia Gavrysh**, Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="95b1b-122">Kabel 创新架构师 Miguel Angel Castejón Dominguez </span><span class="sxs-lookup"><span data-stu-id="95b1b-122">**Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel</span></span>

<span data-ttu-id="95b1b-123">参与者和审阅者：</span><span class="sxs-lookup"><span data-stu-id="95b1b-123">Participants and reviewers:</span></span>

> <span data-ttu-id="95b1b-124">Microsoft .NET 团队高级项目经理 Maira Wenzel </span><span class="sxs-lookup"><span data-stu-id="95b1b-124">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="95b1b-125">Microsoft .NET 文档团队高级内容开发人员 Andy De Gorge </span><span class="sxs-lookup"><span data-stu-id="95b1b-125">**Andy De Gorge**, Senior Content Developer, .NET docs team, Microsoft</span></span>

> <span data-ttu-id="95b1b-126">Microsoft Windows 开发人员平台团队高级项目经理 Miguel Ramos </span><span class="sxs-lookup"><span data-stu-id="95b1b-126">**Miguel Ramos**, Senior Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="95b1b-127">Microsoft Windows 开发人员平台团队首席项目经理 Adam Braden </span><span class="sxs-lookup"><span data-stu-id="95b1b-127">**Adam Braden**, Principal Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="95b1b-128">Microsoft Azure IoT 团队高级项目经理 Ricardo Minguez Pablos </span><span class="sxs-lookup"><span data-stu-id="95b1b-128">**Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT team, Microsoft</span></span>

> <span data-ttu-id="95b1b-129">Nish Anil，Microsoft .NET 团队高级项目经理 </span><span class="sxs-lookup"><span data-stu-id="95b1b-129">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="95b1b-130">Microsoft 高级产品营销经理 Beth Massi </span><span class="sxs-lookup"><span data-stu-id="95b1b-130">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span></span>

> <span data-ttu-id="95b1b-131">Microsoft .NET 团队合作伙伴总监项目经理 Scott Hunter </span><span class="sxs-lookup"><span data-stu-id="95b1b-131">**Scott Hunter**, Partner Director Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="95b1b-132">Marta Fuentes Lara，Kabel </span><span class="sxs-lookup"><span data-stu-id="95b1b-132">**Marta Fuentes Lara**, Kabel</span></span>

> <span data-ttu-id="95b1b-133">Raúl Fernández de Córdoba，Kabel </span><span class="sxs-lookup"><span data-stu-id="95b1b-133">**Raúl Fernández de Córdoba**, Kabel</span></span>

> <span data-ttu-id="95b1b-134">Antonio Manuel Fernández Cantos，Kabel </span><span class="sxs-lookup"><span data-stu-id="95b1b-134">**Antonio Manuel Fernández Cantos**, Kabel</span></span>

## <a name="introduction"></a><span data-ttu-id="95b1b-135">介绍</span><span class="sxs-lookup"><span data-stu-id="95b1b-135">Introduction</span></span>

<span data-ttu-id="95b1b-136">本书介绍了可用于通过现代化路径移动现有桌面应用程序并合并最新的运行时、语言和平台功能的策略。</span><span class="sxs-lookup"><span data-stu-id="95b1b-136">This book is about strategies you can adopt to move your existing desktop applications through the path of modernization and incorporate the latest runtime, language, and platform features.</span></span> <span data-ttu-id="95b1b-137">你会发现，由于每个应用程序不同，并且你的要求和偏好也不同，因此没有独特的方法。</span><span class="sxs-lookup"><span data-stu-id="95b1b-137">You'll discover that there's no unique recipe as each application is different, and so are your requirements and preferences.</span></span> <span data-ttu-id="95b1b-138">好消息是有一些常用的方法可用于向应用程序添加新特性和功能。</span><span class="sxs-lookup"><span data-stu-id="95b1b-138">The good news is that there are common approaches you can apply to add new features and capabilities to your applications.</span></span> <span data-ttu-id="95b1b-139">其中一些方法甚至不需要对代码进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="95b1b-139">Some of them won't even require major modifications of your code.</span></span> <span data-ttu-id="95b1b-140">本书介绍了所有这些功能在后台的工作原理，并说明了其实现机制。</span><span class="sxs-lookup"><span data-stu-id="95b1b-140">In this book, we'll reveal how all those features work behind the scenes and explain the mechanics of their implementations.</span></span> <span data-ttu-id="95b1b-141">此外，本书还详细介绍了一些对现有桌面应用程序进行现代化改造的常见场景，以便你可以找到发展项目的灵感。</span><span class="sxs-lookup"><span data-stu-id="95b1b-141">Moreover, you'll find some common scenarios for modernizing existing desktop applications shown in detail so you can find inspiration for evolving your projects.</span></span>

<span data-ttu-id="95b1b-142">Microsoft 对现有应用程序进行现代化改造的方法是让你能够灵活地创建自己的自定义路径。</span><span class="sxs-lookup"><span data-stu-id="95b1b-142">Microsoft's approach to modernizing existing applications is to give you the flexibility to create your own customized path.</span></span> <span data-ttu-id="95b1b-143">本书中所述的所有现代化策略多是独立的。</span><span class="sxs-lookup"><span data-stu-id="95b1b-143">All the modernization strategies described in this book are mostly independent.</span></span> <span data-ttu-id="95b1b-144">你可以选择与你的应用程序相关的策略，跳过对你不重要的其他策略。</span><span class="sxs-lookup"><span data-stu-id="95b1b-144">You can choose ones that are relevant for your application and skip others that aren't important for you.</span></span> <span data-ttu-id="95b1b-145">换句话说，你可以混合搭配策略以最好地满足你的应用程序需求。</span><span class="sxs-lookup"><span data-stu-id="95b1b-145">In other words, you can mix and match the strategies to best address your application needs.</span></span>

## <a name="who-should-use-the-book"></a><span data-ttu-id="95b1b-146">本书的目标读者</span><span class="sxs-lookup"><span data-stu-id="95b1b-146">Who should use the book</span></span>

<span data-ttu-id="95b1b-147">我们为希望通过对现有 Windows Forms 和 WPF 桌面应用程序进行现代化改造以利用 .NET Core 和 Windows 10 好处的开发人员和解决方案架构师编写本书。</span><span class="sxs-lookup"><span data-stu-id="95b1b-147">We wrote this book for developers and solution architects who want to modernize existing Windows Forms and WPF desktop applications to leverage the benefits of .NET Core and Windows 10.</span></span>

<span data-ttu-id="95b1b-148">如果你是一位技术决策制定者（例如需要大致了解更新现有桌面应用程序的好处的企业架构师、开发主管或主管），你也可能会发现本书非常有用。</span><span class="sxs-lookup"><span data-stu-id="95b1b-148">You might also find this book useful if you're a technical decision maker, such as an enterprise architect or a development lead or director who wants an overview of the benefits of updating existing desktop applications.</span></span>

## <a name="how-to-use-the-book"></a><span data-ttu-id="95b1b-149">如何使用本书</span><span class="sxs-lookup"><span data-stu-id="95b1b-149">How to use the book</span></span>

<span data-ttu-id="95b1b-150">本书介绍了需要对现有应用程序进行现代化改造的原因，以及使用 NET Core 3.1 和 MSIX 对桌面应用进行现代化改造的具体好处。</span><span class="sxs-lookup"><span data-stu-id="95b1b-150">This book addresses the "why"—why you might want to modernize your existing applications, and the specific benefits you get from using NET Core 3.1 and MSIX to modernize your desktop apps.</span></span> <span data-ttu-id="95b1b-151">本书的内容适用于架构师和技术决策者，他们只需大概了解，不需要实现和技术分步细节。</span><span class="sxs-lookup"><span data-stu-id="95b1b-151">The content of the book is designed for architects and technical decision makers who want an overview, but who don't need to focus on implementation and technical, step-by-step details.</span></span>

<span data-ttu-id="95b1b-152">不同的章节还提供了示例实现代码片段和屏幕截图，第 5 章专门介绍了示例应用程序的完整迁移过程。</span><span class="sxs-lookup"><span data-stu-id="95b1b-152">Along the different chapters, sample implementation code snippets and screenshots are provided, with chapter 5 devoted to showcase a complete migration process for sample applications.</span></span>

## <a name="what-this-book-doesnt-cover"></a><span data-ttu-id="95b1b-153">本书未涵盖的内容</span><span class="sxs-lookup"><span data-stu-id="95b1b-153">What this book doesn't cover</span></span>

<span data-ttu-id="95b1b-154">本书介绍了一些特定的场景（侧重于直接迁移场景），其中概述了利用现代化改造的好处且不需要重写代码的方法。</span><span class="sxs-lookup"><span data-stu-id="95b1b-154">This book covers a specific subset of scenarios that are focused on lift-and-shift scenarios, outlining the way to gain the benefits of modernizing without the effort of rewriting code.</span></span>

<span data-ttu-id="95b1b-155">本书并未介绍如何使用 .NET Core 从头开始开发新式应用程序，也未介绍 Windows 窗体和 WPF 使用入门。</span><span class="sxs-lookup"><span data-stu-id="95b1b-155">This book isn't about developing modern applications with .NET Core from scratch or about getting started with Windows Forms and WPF.</span></span> <span data-ttu-id="95b1b-156">它重点介绍如何通过最新的桌面开发技术来更新现有桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="95b1b-156">It focuses on how you can update existing desktop applications with the latest technologies for desktop development.</span></span>

## <a name="samples-used-in-this-book"></a><span data-ttu-id="95b1b-157">本书中使用的示例</span><span class="sxs-lookup"><span data-stu-id="95b1b-157">Samples used in this book</span></span>

<span data-ttu-id="95b1b-158">为了强调执行现代化改造所需的步骤，我们将使用名为 `eShopModernizing` 的示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="95b1b-158">To highlight the necessary steps to perform a modernization, we'll be using a sample application called `eShopModernizing`.</span></span> <span data-ttu-id="95b1b-159">此应用程序有两种样式（Windows 窗体和 WPF），我们将分步介绍如何使用 .NET Core 针对这两种风格进行现代化改造。</span><span class="sxs-lookup"><span data-stu-id="95b1b-159">This application has two flavors, Windows Forms and WPF, and we'll show a step-by-step process on how to perform the modernization on both of them to .NET Core.</span></span>

<span data-ttu-id="95b1b-160">此外，在本书的 GitHub 存储库中，你会发现该过程的结果，如果你决定按照分步教程操作，则可以将其用作参考。</span><span class="sxs-lookup"><span data-stu-id="95b1b-160">Also, on the GitHub repository for this book, you'll find the results of the process, which you can consult with if you decide to follow the step-by-step tutorial.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="95b1b-161">提供你的反馈</span><span class="sxs-lookup"><span data-stu-id="95b1b-161">Send your feedback</span></span>

<span data-ttu-id="95b1b-162">我们正在不断完善本书和相关示例，欢迎你提供反馈！</span><span class="sxs-lookup"><span data-stu-id="95b1b-162">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="95b1b-163">如果对如何改进本书有任何建议，请使用 [GitHub 问题](https://github.com/dotnet/docs/issues)上任何页面底部的反馈部分进行反馈。</span><span class="sxs-lookup"><span data-stu-id="95b1b-163">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="95b1b-164">下一页</span><span class="sxs-lookup"><span data-stu-id="95b1b-164">Next</span></span>](why-modern-applications.md)
