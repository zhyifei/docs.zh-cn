---
title: "对 .NET Framework 应用程序进行全球化和本地化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- international applications [.NET Framework]
- globalization [.NET Framework], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET Framework], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
caps.latest.revision: "42"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 63f0e001280773c55f18f0604ca93986acbb9674
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="globalizing-and-localizing-net-framework-applications"></a><span data-ttu-id="5957b-102">对 .NET Framework 应用程序进行全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="5957b-102">Globalizing and Localizing .NET Framework Applications</span></span>
<span data-ttu-id="5957b-103">开发[全球通用的应用程序](http://msdn.microsoft.com/goglobal/bb978433.aspx)（包括可本地化为一种或多种语言的应用程序）分为三步：全球化、可本地化性审核和本地化。</span><span class="sxs-lookup"><span data-stu-id="5957b-103">Developing a [world-ready application](http://msdn.microsoft.com/goglobal/bb978433.aspx), including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>  
  
 [<span data-ttu-id="5957b-104">全球化</span><span class="sxs-lookup"><span data-stu-id="5957b-104">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="5957b-105">此步骤包括设计和编码非特定区域性和非特定语言的应用程序，以及设计和编码支持所有用户的本地化用户界面和区域数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5957b-105">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="5957b-106">它涉及做出不基于区域性特定的假设的设计和编程决策。</span><span class="sxs-lookup"><span data-stu-id="5957b-106">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="5957b-107">虽然全球化应用程序未本地化，但它经过设计和编写，因此随后可相对容易地将其本地化为一种或多种语言。</span><span class="sxs-lookup"><span data-stu-id="5957b-107">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>  
  
 [<span data-ttu-id="5957b-108">可本地化性审核</span><span class="sxs-lookup"><span data-stu-id="5957b-108">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="5957b-109">此步骤包括评审应用程序的代码和设计，以确保能轻松本地化应用程序和标识本地化的潜在障碍，并验证应用程序的可执行代码是否与其资源分隔开。</span><span class="sxs-lookup"><span data-stu-id="5957b-109">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="5957b-110">如果全球化阶段有效，则本地化检查将确认全球化过程中做出的设计和编码选择。</span><span class="sxs-lookup"><span data-stu-id="5957b-110">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="5957b-111">本地化阶段还可以标识任何遗留问题，以便在本地化阶段不必修改应用程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="5957b-111">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>  
  
 [<span data-ttu-id="5957b-112">本地化</span><span class="sxs-lookup"><span data-stu-id="5957b-112">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="5957b-113">此步骤包括为特定区域性或区域自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="5957b-113">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="5957b-114">如果已正确执行全球化和本地化分析这两个步骤，则本地化主要包括用户界面的翻译。</span><span class="sxs-lookup"><span data-stu-id="5957b-114">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>  
  
 <span data-ttu-id="5957b-115">遵循这三个步骤有两大好处：</span><span class="sxs-lookup"><span data-stu-id="5957b-115">Following these three steps provides two advantages:</span></span>  
  
-   <span data-ttu-id="5957b-116">让你无需改进为支持单个区域性（如美国英语）而专门设计的应用程序以支持其他区域性。英语，以支持其他区域性。</span><span class="sxs-lookup"><span data-stu-id="5957b-116">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>  
  
-   <span data-ttu-id="5957b-117">这会产生更加稳定并有少量 Bug 的本地化应用程序。</span><span class="sxs-lookup"><span data-stu-id="5957b-117">It results in localized applications that are more stable and have fewer bugs.</span></span>  
  
 <span data-ttu-id="5957b-118">.NET Framework 为开发全球通用和本地化的应用程序提供了广泛支持。</span><span class="sxs-lookup"><span data-stu-id="5957b-118">The .NET Framework provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="5957b-119">特别是，.NET Framework 类库中许多类成员通过返回可反映当前用户区域性或指定区域性约定的值来帮助全球化。</span><span class="sxs-lookup"><span data-stu-id="5957b-119">In particular, many type members in the .NET Framework class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="5957b-120">此外，.NET Framework 支持附属程序集，这可推动本地化应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="5957b-120">Also, the .NET Framework supports satellite assemblies, which facilitate the process of localizing an application.</span></span>  
  
 <span data-ttu-id="5957b-121">有关其他信息，请参见[全球化文档](/globalization/)。</span><span class="sxs-lookup"><span data-stu-id="5957b-121">For additional information, see the [Globalization documentation](/globalization/).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5957b-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="5957b-122">In This Section</span></span>  
 [<span data-ttu-id="5957b-123">全球化</span><span class="sxs-lookup"><span data-stu-id="5957b-123">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="5957b-124">讨论创建全球通用的应用程序的第一个阶段，该阶段包括设计和编码为非特定区域性和非特定语言的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5957b-124">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>  
  
 [<span data-ttu-id="5957b-125">可本地化性审核</span><span class="sxs-lookup"><span data-stu-id="5957b-125">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="5957b-126">讨论创建本地化应用程序的第二个阶段，该阶段包含标识本地化的潜在路障。</span><span class="sxs-lookup"><span data-stu-id="5957b-126">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>  
  
 [<span data-ttu-id="5957b-127">本地化</span><span class="sxs-lookup"><span data-stu-id="5957b-127">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="5957b-128">讨论创建本地化应用程序的最后阶段，该阶段包含自定义应用程序的特定区域或区域性的用户界面。</span><span class="sxs-lookup"><span data-stu-id="5957b-128">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>  
  
 [<span data-ttu-id="5957b-129">不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="5957b-129">Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="5957b-130">描述默认情况下如何使用区分区域性的 .NET Framework 方法和类来获得不区分区域性的结果。</span><span class="sxs-lookup"><span data-stu-id="5957b-130">Describes how to use .NET Framework methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>  
  
 [<span data-ttu-id="5957b-131">开发全球通用应用程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="5957b-131">Best Practices for Developing World-Ready Applications</span></span>](../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)  
 <span data-ttu-id="5957b-132">描述在全球化、本地化和开发全球通用的 ASP.NET 应用程序时遵循的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="5957b-132">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5957b-133">参考</span><span class="sxs-lookup"><span data-stu-id="5957b-133">Reference</span></span>  
 <span data-ttu-id="5957b-134"><xref:System.Globalization?displayProperty=nameWithType> 命名空间</span><span class="sxs-lookup"><span data-stu-id="5957b-134"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>  
 <span data-ttu-id="5957b-135">包含定义区域性相关信息的类，这些信息包括语言、国家/地区、正在使用的日历、日期的格式模式、货币、数字以及字符串的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="5957b-135">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>  
  
 <span data-ttu-id="5957b-136"><xref:System.Resources> 命名空间</span><span class="sxs-lookup"><span data-stu-id="5957b-136"><xref:System.Resources> namespace</span></span>  
 <span data-ttu-id="5957b-137">提供用于创建、操作和使用资源的类。</span><span class="sxs-lookup"><span data-stu-id="5957b-137">Provides classes for creating, manipulating, and using resources.</span></span>  
  
 <span data-ttu-id="5957b-138"><xref:System.Text> 命名空间</span><span class="sxs-lookup"><span data-stu-id="5957b-138"><xref:System.Text> namespace</span></span>  
 <span data-ttu-id="5957b-139">包含表示 ASCII、ANSI、Unicode 以及其他字符编码的类。</span><span class="sxs-lookup"><span data-stu-id="5957b-139">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>  
  
 [<span data-ttu-id="5957b-140">Resgen.exe（资源文件生成器）</span><span class="sxs-lookup"><span data-stu-id="5957b-140">Resgen.exe (Resource File Generator)</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 <span data-ttu-id="5957b-141">描述如何使用 Resgen.exe 将 .txt 文件和基于 XML 的资源格式 (.resx) 文件转换为公共语言运行时二进制 .resources 文件。</span><span class="sxs-lookup"><span data-stu-id="5957b-141">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>  
  
 [<span data-ttu-id="5957b-142">Winres.exe（Windows 窗体资源编辑器）</span><span class="sxs-lookup"><span data-stu-id="5957b-142">Winres.exe (Windows Forms Resource Editor)</span></span>](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 <span data-ttu-id="5957b-143">描述如何使用 Winres.exe 本地化 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="5957b-143">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>
