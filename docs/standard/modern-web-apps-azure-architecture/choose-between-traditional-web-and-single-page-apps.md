---
title: "传统 web 应用程序和单页面应用程序之间进行选择"
description: "使用 ASP.NET 核心和 Microsoft Azure 的架构师现代 web 应用程序"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: eb830ede1b644700a80f0e9fac2f3608deb88276
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a><span data-ttu-id="dc01a-103">传统 Web 应用程序和单页面应用程序 (Spa) 之间进行选择</span><span class="sxs-lookup"><span data-stu-id="dc01a-103">Choose Between Traditional Web Apps and Single Page Apps (SPAs)</span></span>

> <span data-ttu-id="dc01a-104">"Atwood 的法律： 任何应用程序可以编写在 JavaScript 中，将最终用 JavaScript 编写。"</span><span class="sxs-lookup"><span data-stu-id="dc01a-104">"Atwood's Law: Any application that can be written in JavaScript, will eventually be written in JavaScript."</span></span>  
> <span data-ttu-id="dc01a-105">_\- Jeff Atwood_</span><span class="sxs-lookup"><span data-stu-id="dc01a-105">_\- Jeff Atwood_</span></span>

## <a name="summary"></a><span data-ttu-id="dc01a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="dc01a-106">Summary</span></span>

<span data-ttu-id="dc01a-107">到目前构建 web 应用程序的两种常规方法： 单页面应用程序 (Spa) 在 web 浏览器中执行大部分的用户界面逻辑服务器执行大多数应用程序逻辑的传统 web 应用程序与主要使用 web Api 的 web 服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="dc01a-107">There are two general approaches to building web applications today: traditional web applications that perform most of the application logic on the server, and single page applications (SPAs) that perform most of the user interface logic in a web browser, communicating with the web server primarily using web APIs.</span></span> <span data-ttu-id="dc01a-108">也可以混合方法，最简单正在承载一个或多个丰富类似 SPA 的子应用程序中的较大的传统 web 应用。</span><span class="sxs-lookup"><span data-stu-id="dc01a-108">A hybrid approach is also possible, the simplest being host one or more rich SPA-like sub-applications within a larger traditional web application.</span></span>

<span data-ttu-id="dc01a-109">你应使用传统 web 应用程序时：</span><span class="sxs-lookup"><span data-stu-id="dc01a-109">You should use traditional web applications when:</span></span>

-   <span data-ttu-id="dc01a-110">应用程序的客户端要求为简单或甚至是只读的。</span><span class="sxs-lookup"><span data-stu-id="dc01a-110">Your application's client-side requirements are simple or even read-only.</span></span>

-   <span data-ttu-id="dc01a-111">你的应用程序需要在不支持 JavaScript 的浏览器中正常工作。</span><span class="sxs-lookup"><span data-stu-id="dc01a-111">Your application needs to function in browsers without JavaScript support.</span></span>

-   <span data-ttu-id="dc01a-112">你的团队已熟悉 JavaScript 或 TypeScript 开发技术。</span><span class="sxs-lookup"><span data-stu-id="dc01a-112">Your team is unfamiliar with JavaScript or TypeScript development techniques.</span></span>

<span data-ttu-id="dc01a-113">应使用 SPA 时：</span><span class="sxs-lookup"><span data-stu-id="dc01a-113">You should use a SPA when:</span></span>

-   <span data-ttu-id="dc01a-114">你的应用程序必须公开具有许多功能的丰富的用户接口。</span><span class="sxs-lookup"><span data-stu-id="dc01a-114">Your application must expose a rich user interface with many features.</span></span>

-   <span data-ttu-id="dc01a-115">熟悉 JavaScript 和/或 TypeScript 开发你的团队。</span><span class="sxs-lookup"><span data-stu-id="dc01a-115">Your team is familiar with JavaScript and/or TypeScript development.</span></span>

-   <span data-ttu-id="dc01a-116">你的应用程序必须已公开其他 （内部或公共） 的客户端的 api 的 API。</span><span class="sxs-lookup"><span data-stu-id="dc01a-116">Your application must already expose an API for other (internal or public) clients.</span></span>

<span data-ttu-id="dc01a-117">此外，SPA 框架要求更大体系结构和安全专业知识。</span><span class="sxs-lookup"><span data-stu-id="dc01a-117">Additionally, SPA frameworks require greater architectural and security expertise.</span></span> <span data-ttu-id="dc01a-118">遇到比传统 web 应用程序由于频繁更新和新框架的更大改动。</span><span class="sxs-lookup"><span data-stu-id="dc01a-118">They experience greater churn due to frequent updates and new frameworks than traditional web applications.</span></span> <span data-ttu-id="dc01a-119">配置自动化的生成和部署进程和利用窗格中列出的部署选项是与 SPA 应用程序比传统 web 应用程序更加困难。</span><span class="sxs-lookup"><span data-stu-id="dc01a-119">Configuring automated build and deployment processes and utilizing deployment options like containers are more difficult with SPA applications than traditional web apps.</span></span>

<span data-ttu-id="dc01a-120">在通过 SPA 模型的用户体验的改进必须权衡这些注意事项。</span><span class="sxs-lookup"><span data-stu-id="dc01a-120">Improvements in user experience made possible by SPA model must be weighed against these considerations.</span></span>

## <a name="when-to-choose-traditional-web-apps"></a><span data-ttu-id="dc01a-121">何时选择传统 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="dc01a-121">When to choose traditional web apps</span></span>

<span data-ttu-id="dc01a-122">下面是选取传统 web 应用程序的以前所述原因的更多详细的说明。</span><span class="sxs-lookup"><span data-stu-id="dc01a-122">The following is a more detailed explanation of the previously-stated reasons for picking traditional web applications.</span></span>

<span data-ttu-id="dc01a-123">**你的应用程序具有简单，可能是只读的、 客户端要求**</span><span class="sxs-lookup"><span data-stu-id="dc01a-123">**Your application has simple, possibly read-only, client-side requirements**</span></span>

<span data-ttu-id="dc01a-124">在以只读方式中，许多 web 应用程序主要由其用户绝大多数消耗。</span><span class="sxs-lookup"><span data-stu-id="dc01a-124">Many web applications are primarily consumed in a read-only fashion by the vast majority of their users.</span></span> <span data-ttu-id="dc01a-125">只读 （或读取主要） 应用程序往往比那些维护和操作状态的大量简单得多。</span><span class="sxs-lookup"><span data-stu-id="dc01a-125">Read-only (or read-mostly) applications tend to be much simpler than those that maintain and manipulate a great deal of state.</span></span> <span data-ttu-id="dc01a-126">例如，搜索引擎可能包括单一入口点与文本框中显示搜索结果的第二个页。</span><span class="sxs-lookup"><span data-stu-id="dc01a-126">For example, a search engine might consist of a single entry point with a textbox and a second page for displaying search results.</span></span> <span data-ttu-id="dc01a-127">匿名用户可以轻松地请求，并且没有很少需要客户端逻辑。</span><span class="sxs-lookup"><span data-stu-id="dc01a-127">Anonymous users can easily make requests, and there is little need for client-side logic.</span></span> <span data-ttu-id="dc01a-128">同样，博客或内容管理系统的面向公众的应用程序通常包含主要的使用很少的客户端行为的内容。</span><span class="sxs-lookup"><span data-stu-id="dc01a-128">Likewise, a blog or content management system's public-facing application usually consists mainly of content with little client-side behavior.</span></span> <span data-ttu-id="dc01a-129">此类应用程序轻松构建为 web 服务器上执行逻辑和呈现 HTML 浏览器中显示的传统的基于服务器的 web 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="dc01a-129">Such applications are easily built as traditional server-based web applications which perform logic on the web server and render HTML to be displayed in the browser.</span></span> <span data-ttu-id="dc01a-130">该站点的每个唯一页拥有自己的 URL 可标有书签并按搜索引擎索引 （默认情况下，而无需添加此作为独立的功能的应用程序） 也是此类情况下的一个明显好处。</span><span class="sxs-lookup"><span data-stu-id="dc01a-130">The fact that each unique page of the site has its own URL that can be bookmarked and indexed by search engines (by default, without having to add this as a separate feature of the application) is also a clear benefit in such scenarios.</span></span>

<span data-ttu-id="dc01a-131">**你的应用程序需要在不支持 JavaScript 的浏览器中正常工作**</span><span class="sxs-lookup"><span data-stu-id="dc01a-131">**Your application needs to function in browsers without JavaScript support**</span></span>

<span data-ttu-id="dc01a-132">需要能够在有限或者没有支持 JavaScript 的浏览器的 web 应用程序应使用传统 web 应用程序工作流编写的 （或至少能够故障回复到这种行为）。</span><span class="sxs-lookup"><span data-stu-id="dc01a-132">Web applications that need to function in browsers with limited or no JavaScript support should be written using traditional web app workflows (or at least be able to fall back to such behavior).</span></span> <span data-ttu-id="dc01a-133">Spa 才能正常; 需要客户端 JavaScript如果不可用，Spa 不是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="dc01a-133">SPAs require client-side JavaScript in order to function; if it's not available, SPAs are not a good choice.</span></span>

<span data-ttu-id="dc01a-134">**你的团队已熟悉 JavaScript 或 TypeScript 开发技术**</span><span class="sxs-lookup"><span data-stu-id="dc01a-134">**Your team is unfamiliar with JavaScript or TypeScript development techniques**</span></span>

<span data-ttu-id="dc01a-135">如果你的团队是熟悉 JavaScript 或 TypeScript，但熟悉服务器端 web 应用程序开发，则它们可能将能够比 SPA 更快速地交付的传统 web 应用。</span><span class="sxs-lookup"><span data-stu-id="dc01a-135">If your team is unfamiliar with JavaScript or TypeScript, but is familiar with server-side web application development, then they will probably be able to deliver a traditional web app more quickly than a SPA.</span></span> <span data-ttu-id="dc01a-136">除非学习到程序 Spa 是一个目标，或提供 SPA 的用户体验是必需的传统 web 应用程序均已熟悉生成它们的团队的提高工作效率选择。</span><span class="sxs-lookup"><span data-stu-id="dc01a-136">Unless learning to program SPAs is a goal, or the user experience afforded by a SPA is required, traditional web apps are a more productive choice for teams who are already familiar with building them.</span></span>

## <a name="when-to-choose-spas"></a><span data-ttu-id="dc01a-137">何时选择 Spa</span><span class="sxs-lookup"><span data-stu-id="dc01a-137">When to choose SPAs</span></span>

<span data-ttu-id="dc01a-138">下面是开发的更多详细的说明何时选择单页面应用程序样式的 web 应用。</span><span class="sxs-lookup"><span data-stu-id="dc01a-138">The following is a more detailed explanation of when to choose a Single Page Applications style of development for your web app.</span></span>

<span data-ttu-id="dc01a-139">**你的应用程序必须公开具有许多功能的丰富的用户接口**</span><span class="sxs-lookup"><span data-stu-id="dc01a-139">**Your application must expose a rich user interface with many features**</span></span>

<span data-ttu-id="dc01a-140">Spa 可以支持不需要重新加载该页面，因为用户执行的操作或应用程序的区域之间导航的丰富客户端功能。</span><span class="sxs-lookup"><span data-stu-id="dc01a-140">SPAs can support rich client-side functionality that doesn't require reloading the page as users take actions or navigate between areas of the app.</span></span> <span data-ttu-id="dc01a-141">Spa 可以加载更快地，提取在后台的数据和单个用户操作是更快地响应，因为完整的页面重新加载需要很少出现。</span><span class="sxs-lookup"><span data-stu-id="dc01a-141">SPAs can load more quickly, fetching data in the background, and individual user actions are more responsive since full page reloads are rare.</span></span> <span data-ttu-id="dc01a-142">Spa 可以支持增量更新，用户无需单击一个按钮以提交表格保存部分完成窗体或文档。</span><span class="sxs-lookup"><span data-stu-id="dc01a-142">SPAs can support incremental updates, saving partially completed forms or documents without the user having to click a button to submit a form.</span></span> <span data-ttu-id="dc01a-143">Spa 可以比传统的应用程序更轻松地支持丰富的客户端行为，如拖动和删除。</span><span class="sxs-lookup"><span data-stu-id="dc01a-143">SPAs can support rich client-side behaviors, such as drag-and-drop, much more readily than traditional applications.</span></span> <span data-ttu-id="dc01a-144">Spa 可以用于对重新建立连接后最终同步回发到服务器的客户端模型进行更新以断开连接模式运行。</span><span class="sxs-lookup"><span data-stu-id="dc01a-144">SPAs can be designed to run in a disconnected mode, making updates to a client-side model that are eventually synchronized back to the server once a connection is re-established.</span></span> <span data-ttu-id="dc01a-145">如果您的应用程序的要求包括超出典型 HTML 窗体提供的丰富功能，则应选择 SPA 样式的应用程序。</span><span class="sxs-lookup"><span data-stu-id="dc01a-145">You should choose a SPA style application if your app's requirements include rich functionality that goes beyond what typical HTML forms offer.</span></span>

<span data-ttu-id="dc01a-146">请注意，经常需要实现功能内置于传统 web 应用程序，如在地址栏反映当前的操作 （并允许到书签的用户或深层链接到此 URL，以返回到它） 中显示有意义的 URL 的 Spa。</span><span class="sxs-lookup"><span data-stu-id="dc01a-146">Note that frequently SPAs need to implement features that are built-in to traditional web apps, such as displaying a meaningful URL in the address bar reflecting the current operation (and allowing users to bookmark or deep link to this URL to return to it).</span></span> <span data-ttu-id="dc01a-147">Spa 还应允许用户用于浏览器的后退和前进按钮不会意外它们的结果。</span><span class="sxs-lookup"><span data-stu-id="dc01a-147">SPAs also should allow users to use the browser's back and forward buttons with results that won't surprise them.</span></span>

<span data-ttu-id="dc01a-148">**你的团队已熟悉 JavaScript 和/或 TypeScript 开发**</span><span class="sxs-lookup"><span data-stu-id="dc01a-148">**Your team is familiar with JavaScript and/or TypeScript development**</span></span>

<span data-ttu-id="dc01a-149">编写 Spa 需要熟悉 JavaScript 和/或 TypeScript 和客户端编程技术和库。</span><span class="sxs-lookup"><span data-stu-id="dc01a-149">Writing SPAs requires familiarity with JavaScript and/or TypeScript and client-side programming techniques and libraries.</span></span> <span data-ttu-id="dc01a-150">团队应在编写现代 JavaScript 使用角这样的 SPA 框架功能完善。</span><span class="sxs-lookup"><span data-stu-id="dc01a-150">Your team should be competent in writing modern JavaScript using a SPA framework like Angular.</span></span>

> ### <a name="references--spa-frameworks"></a><span data-ttu-id="dc01a-151">引用 – SPA 框架</span><span class="sxs-lookup"><span data-stu-id="dc01a-151">References – SPA Frameworks</span></span>
> - <span data-ttu-id="dc01a-152">**AngularJS**</span><span class="sxs-lookup"><span data-stu-id="dc01a-152">**AngularJS**</span></span>  
> <span data-ttu-id="dc01a-153"><https://angularjs.org/></span><span class="sxs-lookup"><span data-stu-id="dc01a-153"><https://angularjs.org/></span></span>
> - <span data-ttu-id="dc01a-154">**4 常用的 JavaScript 框架的比较**</span><span class="sxs-lookup"><span data-stu-id="dc01a-154">**Comparison of 4 Popular JavaScript Frameworks**</span></span>  
> <span data-ttu-id="dc01a-155"><https://www.developereconomics.com/feature-comparison-of-4-popular-js-mv-frameworks></span><span class="sxs-lookup"><span data-stu-id="dc01a-155"><https://www.developereconomics.com/feature-comparison-of-4-popular-js-mv-frameworks></span></span>

<span data-ttu-id="dc01a-156">**你的应用程序必须其他 （内部或公共） 的客户端公开了一个 API**</span><span class="sxs-lookup"><span data-stu-id="dc01a-156">**Your application must already expose an API for other (internal or public) clients**</span></span>

<span data-ttu-id="dc01a-157">如果已正在以供其他客户端支持的 web API，则可能需要较少的工作量创建利用这些 Api，而不是无需复制在服务器端窗体中的逻辑的 SPA 实现。</span><span class="sxs-lookup"><span data-stu-id="dc01a-157">If you're already supporting a web API for use by other clients, it may require less effort to create a SPA implementation that leverages these APIs rather than reproducing the logic in server-side form.</span></span> <span data-ttu-id="dc01a-158">用户与应用程序进行交互，Spa 对查询和更新数据进行广泛使用的 web Api。</span><span class="sxs-lookup"><span data-stu-id="dc01a-158">SPAs make extensive use of web APIs to query and update data as users interact with the application.</span></span>

## <a name="decision-table--traditional-web-or-spa"></a><span data-ttu-id="dc01a-159">决策表 – 传统 Web 或 SPA</span><span class="sxs-lookup"><span data-stu-id="dc01a-159">Decision table – Traditional Web or SPA</span></span>

<span data-ttu-id="dc01a-160">以下的决策表总结了一些传统 web 应用程序和 SPA 之间进行选择时要考虑的基本因素。</span><span class="sxs-lookup"><span data-stu-id="dc01a-160">The following decision table summarizes some of the basic factors to consider when choosing between a traditional web application and a SPA.</span></span>

  | <span data-ttu-id="dc01a-161">**Factor**</span><span class="sxs-lookup"><span data-stu-id="dc01a-161">**Factor**</span></span> | <span data-ttu-id="dc01a-162">**传统 Web 应用**</span><span class="sxs-lookup"><span data-stu-id="dc01a-162">**Traditional Web App**</span></span> | <span data-ttu-id="dc01a-163">**单页面应用程序**</span><span class="sxs-lookup"><span data-stu-id="dc01a-163">**Single Page Application**</span></span> |
  |---|---|---|
  | <span data-ttu-id="dc01a-164">所需的团队熟悉 JavaScript/TypeScript</span><span class="sxs-lookup"><span data-stu-id="dc01a-164">Required Team Familiarity with JavaScript/TypeScript</span></span> | <span data-ttu-id="dc01a-165">最小</span><span class="sxs-lookup"><span data-stu-id="dc01a-165">**Minimal**</span></span> | <span data-ttu-id="dc01a-166">**必需**</span><span class="sxs-lookup"><span data-stu-id="dc01a-166">**Required**</span></span> |
  | <span data-ttu-id="dc01a-167">不带脚本的支持浏览器</span><span class="sxs-lookup"><span data-stu-id="dc01a-167">Support Browsers without Scripting</span></span> | <span data-ttu-id="dc01a-168">**支持**</span><span class="sxs-lookup"><span data-stu-id="dc01a-168">**Supported**</span></span> | <span data-ttu-id="dc01a-169">不支持</span><span class="sxs-lookup"><span data-stu-id="dc01a-169">**Not Supported**</span></span> |
  | <span data-ttu-id="dc01a-170">最小的客户端应用程序行为</span><span class="sxs-lookup"><span data-stu-id="dc01a-170">Minimal Client-Side Application Behavior</span></span> | <span data-ttu-id="dc01a-171">**Well-Suited**</span><span class="sxs-lookup"><span data-stu-id="dc01a-171">**Well-Suited**</span></span> | <span data-ttu-id="dc01a-172">**太过严厉**</span><span class="sxs-lookup"><span data-stu-id="dc01a-172">**Overkill**</span></span> |
  | <span data-ttu-id="dc01a-173">丰富而复杂的用户界面要求</span><span class="sxs-lookup"><span data-stu-id="dc01a-173">Rich, Complex User Interface Requirements</span></span> | <span data-ttu-id="dc01a-174">**限制**</span><span class="sxs-lookup"><span data-stu-id="dc01a-174">**Limited**</span></span> | <span data-ttu-id="dc01a-175">**Well-Suited**</span><span class="sxs-lookup"><span data-stu-id="dc01a-175">**Well-Suited**</span></span> |

>[!div class="step-by-step"]
<span data-ttu-id="dc01a-176">[以前](现代-web 的应用程序-characteristics.md)[下一步](architectural-principles.md)</span><span class="sxs-lookup"><span data-stu-id="dc01a-176">[Previous] (modern-web-applications-characteristics.md) [Next](architectural-principles.md)</span></span>
