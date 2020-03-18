---
title: 常用客户端 Web 技术
description: 使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序 | 常用客户端 Web 技术
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: 2809c8539b42e8e2250039dceed1389b3cbdcd8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449369"
---
# <a name="common-client-side-web-technologies"></a><span data-ttu-id="38332-103">常用客户端 Web 技术</span><span class="sxs-lookup"><span data-stu-id="38332-103">Common client-side web technologies</span></span>

> <span data-ttu-id="38332-104">“优秀的网站应表里如一。”</span><span class="sxs-lookup"><span data-stu-id="38332-104">"Websites should look good from the inside and out."</span></span>  
> <span data-ttu-id="38332-105">_- Paul Cookson_</span><span class="sxs-lookup"><span data-stu-id="38332-105">_- Paul Cookson_</span></span>

<span data-ttu-id="38332-106">ASP.NET Core 应用程序属于 Web 应用程序，并且通常依赖于 HTML、CSS 和 JavaScript 等客户端 Web 技术。</span><span class="sxs-lookup"><span data-stu-id="38332-106">ASP.NET Core applications are web applications and they typically rely on client-side web technologies like HTML, CSS, and JavaScript.</span></span> <span data-ttu-id="38332-107">通过将页面 (HTML) 内容从其布局和样式 (CSS) 以及行为 (JavaScript) 中分离出来，复杂的 Web 应用也可以利用“关注分离”原则。</span><span class="sxs-lookup"><span data-stu-id="38332-107">By separating the content of the page (the HTML) from its layout and styling (the CSS), and its behavior (via JavaScript), complex web apps can leverage the Separation of Concerns principle.</span></span> <span data-ttu-id="38332-108">将来，当这些关注点不相互交织时，可以更轻松地对应用程序的结构、设计或行为进行更改。</span><span class="sxs-lookup"><span data-stu-id="38332-108">Future changes to the structure, design, or behavior of the application can be made more easily when these concerns are not intertwined.</span></span>

<span data-ttu-id="38332-109">尽管 HTML 和 CSS 相对稳定，但应用程序框架和实用程序开发人员用于生成基于 Web 的应用程序的 JavaScript，正以惊人的速度发展。</span><span class="sxs-lookup"><span data-stu-id="38332-109">While HTML and CSS are relatively stable, JavaScript, by means of the application frameworks and utilities developers work with to build web-based applications, is evolving at breakneck speed.</span></span> <span data-ttu-id="38332-110">本章介绍 Web 开发人员使用 JavaScript 的几种方式，并提供 Angular 和 React 客户端库的简要概述。</span><span class="sxs-lookup"><span data-stu-id="38332-110">This chapter looks at a few ways that JavaScript is used by web developers and provides a high-level overview of the Angular and React client-side libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="38332-111">Blazor 提供了 JavaScript 框架的替代方法，用于生成丰富的交互式客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="38332-111">Blazor provides an alternative to JavaScript frameworks for building rich, interactive client user interfaces.</span></span> <span data-ttu-id="38332-112">客户端 Blazor 支持仍处于预览状态，因此目前不在本章的范围之内。</span><span class="sxs-lookup"><span data-stu-id="38332-112">Client-side Blazor support is still in preview, so for now it's out of scope for this chapter.</span></span>

## <a name="html"></a><span data-ttu-id="38332-113">HTML</span><span class="sxs-lookup"><span data-stu-id="38332-113">HTML</span></span>

<span data-ttu-id="38332-114">HTML 是标准标记语言，用于创建网页和 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="38332-114">HTML is the standard markup language used to create web pages and web applications.</span></span> <span data-ttu-id="38332-115">它的元素组成了网页的构建基块，表示格式化文本、图像、窗体输入和其他结构。</span><span class="sxs-lookup"><span data-stu-id="38332-115">Its elements form the building blocks of pages, representing formatted text, images, form inputs, and other structures.</span></span> <span data-ttu-id="38332-116">浏览器发出 URL 请求时，无论提取网页还是应用程序，首先需要返回 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="38332-116">When a browser makes a request to a URL, whether fetching a page or an application, the first thing that is returned is an HTML document.</span></span> <span data-ttu-id="38332-117">这个 HTML 文档可能引用或包括关于其外观、CSS 形式的布局或 JavaScript 形式的行为的详细信息。</span><span class="sxs-lookup"><span data-stu-id="38332-117">This HTML document may reference or include additional information about its look and layout in the form of CSS, or behavior in the form of JavaScript.</span></span>

## <a name="css"></a><span data-ttu-id="38332-118">CSS</span><span class="sxs-lookup"><span data-stu-id="38332-118">CSS</span></span>

<span data-ttu-id="38332-119">CSS（级联样式表）用于控制 HTML 元素的外观和布局。</span><span class="sxs-lookup"><span data-stu-id="38332-119">CSS (Cascading Style Sheets) is used to control the look and layout of HTML elements.</span></span> <span data-ttu-id="38332-120">CSS 样式可直接应用于 HTML 元素，单独对相同页面进行定义，或在单独文件中定义或由页面引用。</span><span class="sxs-lookup"><span data-stu-id="38332-120">CSS styles can be applied directly to an HTML element, defined separately on the same page, or defined in a separate file and referenced by the page.</span></span> <span data-ttu-id="38332-121">样式根据用于选择给定 HTML 元素的方式进行级联。</span><span class="sxs-lookup"><span data-stu-id="38332-121">Styles cascade based on how they are used to select a given HTML element.</span></span> <span data-ttu-id="38332-122">例如，样式可应用于整个文档，但会由应用于特定元素的样式覆盖。</span><span class="sxs-lookup"><span data-stu-id="38332-122">For instance, a style might apply to an entire document, but would be overridden by a style that applied to a particular element.</span></span> <span data-ttu-id="38332-123">同样，特定于元素的样式会由应用于 CSS 类的样式（曾应用于该元素）覆盖，后者反过来会由指向该元素的特定实例（通过其 ID）的样式覆盖。</span><span class="sxs-lookup"><span data-stu-id="38332-123">Likewise, an element-specific style would be overridden by a style that applied to a CSS class that was applied to the element, which in turn would be overridden by a style targeting a specific instance of that element (via its ID).</span></span> <span data-ttu-id="38332-124">图 6-1</span><span class="sxs-lookup"><span data-stu-id="38332-124">Figure 6-1</span></span>

![CSS 特殊性规则](./media/image6-1.png)

<span data-ttu-id="38332-126">**图 6-1**。</span><span class="sxs-lookup"><span data-stu-id="38332-126">**Figure 6-1.**</span></span> <span data-ttu-id="38332-127">按顺序排列的 CSS 特殊性规则。</span><span class="sxs-lookup"><span data-stu-id="38332-127">CSS Specificity rules, in order.</span></span>

<span data-ttu-id="38332-128">最好将样式保存在单独的样式表文件中，并使用基于选择的级联在应用程序内实现一致且可重用的样式。</span><span class="sxs-lookup"><span data-stu-id="38332-128">It's best to keep styles in their own separate stylesheet files, and to use selection-based cascading to implement consistent and reusable styles within the application.</span></span> <span data-ttu-id="38332-129">应避免将样式规则置于 HTML 中，但将样式（而不是规则）应用于特定的各个元素（不是元素的整个类，也不是应用特定 CSS 类的元素）除外。</span><span class="sxs-lookup"><span data-stu-id="38332-129">Placing style rules within HTML should be avoided, and applying styles to specific individual elements (rather than whole classes of elements, or elements that have had a particular CSS class applied to them) should be the exception, not the rule.</span></span>

### <a name="css-preprocessors"></a><span data-ttu-id="38332-130">CSS 预处理器</span><span class="sxs-lookup"><span data-stu-id="38332-130">CSS preprocessors</span></span>

<span data-ttu-id="38332-131">CSS 样式表缺少对条件逻辑、变量以及其他编程语言功能的支持。</span><span class="sxs-lookup"><span data-stu-id="38332-131">CSS stylesheets lack support for conditional logic, variables, and other programming language features.</span></span> <span data-ttu-id="38332-132">因此，大型样式表通常包含很多重复，如将相同的颜色、字体或其他设置应用于 HTML 元素和 CSS 类的多个不同的变体。</span><span class="sxs-lookup"><span data-stu-id="38332-132">Thus, large stylesheets often include quite a bit of repetition, as the same color, font, or other setting is applied to many different variations of HTML elements and CSS classes.</span></span> <span data-ttu-id="38332-133">通过添加对变量和逻辑的支持，CSS 预处理器可帮助样式表遵循 [DRY 原则](https://deviq.com/don-t-repeat-yourself/)。</span><span class="sxs-lookup"><span data-stu-id="38332-133">CSS preprocessors can help your stylesheets follow the [DRY principle](https://deviq.com/don-t-repeat-yourself/) by adding support for variables and logic.</span></span>

<span data-ttu-id="38332-134">最常用的 CSS 预处理器是 Sass 和 LESS。</span><span class="sxs-lookup"><span data-stu-id="38332-134">The most popular CSS preprocessors are Sass and LESS.</span></span> <span data-ttu-id="38332-135">两者均可扩展 CSS 并与其后向兼容，表示无格式 CSS 文件即为有效的 Sass 或 LESS 文件。</span><span class="sxs-lookup"><span data-stu-id="38332-135">Both extend CSS and are backward compatible with it, meaning that a plain CSS file is a valid Sass or LESS file.</span></span> <span data-ttu-id="38332-136">Sass 基于 Ruby，而 LESS 基于 JavaScript，二者通常作为本地部署过程的一部分运行。</span><span class="sxs-lookup"><span data-stu-id="38332-136">Sass is Ruby-based and LESS is JavaScript based, and both typically run as part of your local development process.</span></span> <span data-ttu-id="38332-137">两者都提供命令行工具，以及 Visual Studio 中的内置支持，可使用 Gulp 或 Grunt 任务运行它们。</span><span class="sxs-lookup"><span data-stu-id="38332-137">Both have command-line tools available, as well as built-in support in Visual Studio for running them using Gulp or Grunt tasks.</span></span>

## <a name="javascript"></a><span data-ttu-id="38332-138">JavaScript</span><span class="sxs-lookup"><span data-stu-id="38332-138">JavaScript</span></span>

<span data-ttu-id="38332-139">JavaScript 是动态的解释性编程语言，已在 ECMAScript 语言规范中进行标准化。</span><span class="sxs-lookup"><span data-stu-id="38332-139">JavaScript is a dynamic, interpreted programming language that has been standardized in the ECMAScript language specification.</span></span> <span data-ttu-id="38332-140">它是 Web 的编程语言。</span><span class="sxs-lookup"><span data-stu-id="38332-140">It is the programming language of the web.</span></span> <span data-ttu-id="38332-141">与 CSS 一样，JavaScript 可定义为 HTML 元素中的属性，作为网页或单独文件中的脚本基块。</span><span class="sxs-lookup"><span data-stu-id="38332-141">Like CSS, JavaScript can be defined as attributes within HTML elements, as blocks of script within a page, or in separate files.</span></span> <span data-ttu-id="38332-142">正如 CSS，建议将 JavaScript 组织到单独的文件中，并尽可能将其与各个网页或应用程序视图中找到的 HTML 分开保存。</span><span class="sxs-lookup"><span data-stu-id="38332-142">Just like CSS, it's recommended to organize JavaScript into separate files, keeping it separated as much as possible from the HTML found on individual web pages or application views.</span></span>

<span data-ttu-id="38332-143">在 Web 应用程序中使用 JavaScript 时，通常需要执行以下几项任务：</span><span class="sxs-lookup"><span data-stu-id="38332-143">When working with JavaScript in your web application, there are a few tasks that you'll commonly need to perform:</span></span>

- <span data-ttu-id="38332-144">选择 HTML 元素并检索和/或更新其值。</span><span class="sxs-lookup"><span data-stu-id="38332-144">Selecting an HTML element and retrieving and/or updating its value.</span></span>

- <span data-ttu-id="38332-145">查询 Web API 以获取数据。</span><span class="sxs-lookup"><span data-stu-id="38332-145">Querying a Web API for data.</span></span>

- <span data-ttu-id="38332-146">向 Web API 发送命令（并使用其结果响应回叫）。</span><span class="sxs-lookup"><span data-stu-id="38332-146">Sending a command to a Web API (and responding to a callback with its result).</span></span>

- <span data-ttu-id="38332-147">执行验证。</span><span class="sxs-lookup"><span data-stu-id="38332-147">Performing validation.</span></span>

<span data-ttu-id="38332-148">可以仅使用 JavaScript 执行上述所有任务，但存在的许多库可简化这些任务。</span><span class="sxs-lookup"><span data-stu-id="38332-148">You can perform all of these tasks with JavaScript alone, but many libraries exist to make these tasks easier.</span></span> <span data-ttu-id="38332-149">其中一个，也是最成功的库是 jQuery，仍是在网页上简化这些任务的热门选择。</span><span class="sxs-lookup"><span data-stu-id="38332-149">One of the first and most successful of these libraries is jQuery, which continues to be a popular choice for simplifying these tasks on web pages.</span></span> <span data-ttu-id="38332-150">对于单页应用程序 (SPA)，jQuery 不会提供 Angular 和 React 提供的众多所需功能。</span><span class="sxs-lookup"><span data-stu-id="38332-150">For Single Page Applications (SPAs), jQuery doesn't provide many of the desired features that Angular and React offer.</span></span>

### <a name="legacy-web-apps-with-jquery"></a><span data-ttu-id="38332-151">使用 jQuery 的旧版 Web 应用</span><span class="sxs-lookup"><span data-stu-id="38332-151">Legacy web apps with jQuery</span></span>

<span data-ttu-id="38332-152">尽管 jQuery 基于古老的 JavaScript 框架标准，但它仍然是常用的库，用于处理 HTML/CSS 和生成对 Web API 进行 AJAX 调用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="38332-152">Although ancient by JavaScript framework standards, jQuery continues to be a commonly used library for working with HTML/CSS and building applications that make AJAX calls to web APIs.</span></span> <span data-ttu-id="38332-153">但是，jQuery 按浏览器文档对象模型 (DOM) 级别操作，并默认只提供命令性，而不是声明性的模型。</span><span class="sxs-lookup"><span data-stu-id="38332-153">However, jQuery operates at the level of the browser document object model (DOM), and by default offers only an imperative, rather than declarative, model.</span></span>

<span data-ttu-id="38332-154">例如，假设一个文本框的值超过 10，则应使页面上的元素可见。</span><span class="sxs-lookup"><span data-stu-id="38332-154">For example, imagine that if a textbox's value exceeds 10, an element on the page should be made visible.</span></span> <span data-ttu-id="38332-155">在 jQuery 中，此操作通常通过使用检查文本框的值，并根据该值设置目标元素可见性的代码编写事件处理程序来实现。</span><span class="sxs-lookup"><span data-stu-id="38332-155">In jQuery, this would typically be implemented by writing an event handler with code that would inspect the textbox's value and set the visibility of the target element based on that value.</span></span> <span data-ttu-id="38332-156">这是一种基于代码的命令性方法。</span><span class="sxs-lookup"><span data-stu-id="38332-156">This is an imperative, code-based approach.</span></span> <span data-ttu-id="38332-157">另一种框架可能转而使用数据绑定，以声明的方式将元素的可见性与文本框值绑定。</span><span class="sxs-lookup"><span data-stu-id="38332-157">Another framework might instead use databinding to bind the visibility of the element to the value of the textbox declaratively.</span></span> <span data-ttu-id="38332-158">这种方法不需要编写任何代码，改为只需要修饰数据绑定属性涉及的元素。</span><span class="sxs-lookup"><span data-stu-id="38332-158">This would not require writing any code, but instead only requires decorating the elements involved with data binding attributes.</span></span> <span data-ttu-id="38332-159">随着客户端行为变得更加复杂，数据绑定方法经常成为更简单的解决方案，其包含的代码和条件复杂性也较少。</span><span class="sxs-lookup"><span data-stu-id="38332-159">As client-side behaviors grow more complex, data binding approaches frequently result in simpler solutions with less code and conditional complexity.</span></span>

### <a name="jquery-vs-a-spa-framework"></a><span data-ttu-id="38332-160">jQuery 与 SPA Framework</span><span class="sxs-lookup"><span data-stu-id="38332-160">jQuery vs a SPA Framework</span></span>

| <span data-ttu-id="38332-161">**因素**</span><span class="sxs-lookup"><span data-stu-id="38332-161">**Factor**</span></span> | <span data-ttu-id="38332-162">**jQuery**</span><span class="sxs-lookup"><span data-stu-id="38332-162">**jQuery**</span></span> | <span data-ttu-id="38332-163">**Angular**</span><span class="sxs-lookup"><span data-stu-id="38332-163">**Angular**</span></span>|
|--------------------------|------------|-------------|
| <span data-ttu-id="38332-164">抽象 DOM</span><span class="sxs-lookup"><span data-stu-id="38332-164">Abstracts the DOM</span></span> | <span data-ttu-id="38332-165">**是**</span><span class="sxs-lookup"><span data-stu-id="38332-165">**Yes**</span></span> | <span data-ttu-id="38332-166">**是**</span><span class="sxs-lookup"><span data-stu-id="38332-166">**Yes**</span></span> |
| <span data-ttu-id="38332-167">AJAX 支持</span><span class="sxs-lookup"><span data-stu-id="38332-167">AJAX Support</span></span> | <span data-ttu-id="38332-168">**是**</span><span class="sxs-lookup"><span data-stu-id="38332-168">**Yes**</span></span> | <span data-ttu-id="38332-169">**是**</span><span class="sxs-lookup"><span data-stu-id="38332-169">**Yes**</span></span> |
| <span data-ttu-id="38332-170">声明性数据绑定</span><span class="sxs-lookup"><span data-stu-id="38332-170">Declarative Data Binding</span></span> | <span data-ttu-id="38332-171">**否**</span><span class="sxs-lookup"><span data-stu-id="38332-171">**No**</span></span> | <span data-ttu-id="38332-172">**是**</span><span class="sxs-lookup"><span data-stu-id="38332-172">**Yes**</span></span> |
| <span data-ttu-id="38332-173">MVC 样式路由</span><span class="sxs-lookup"><span data-stu-id="38332-173">MVC-style Routing</span></span> | <span data-ttu-id="38332-174">**否**</span><span class="sxs-lookup"><span data-stu-id="38332-174">**No**</span></span> | <span data-ttu-id="38332-175">**是**</span><span class="sxs-lookup"><span data-stu-id="38332-175">**Yes**</span></span> |
| <span data-ttu-id="38332-176">模板化</span><span class="sxs-lookup"><span data-stu-id="38332-176">Templating</span></span> | <span data-ttu-id="38332-177">**否**</span><span class="sxs-lookup"><span data-stu-id="38332-177">**No**</span></span> | <span data-ttu-id="38332-178">**是**</span><span class="sxs-lookup"><span data-stu-id="38332-178">**Yes**</span></span> |
| <span data-ttu-id="38332-179">深层链接路由</span><span class="sxs-lookup"><span data-stu-id="38332-179">Deep-Link Routing</span></span> | <span data-ttu-id="38332-180">**否**</span><span class="sxs-lookup"><span data-stu-id="38332-180">**No**</span></span> | <span data-ttu-id="38332-181">**是**</span><span class="sxs-lookup"><span data-stu-id="38332-181">**Yes**</span></span> |

<span data-ttu-id="38332-182">本质上，jQuery 缺少的大多数功能均可通过添加其他库进行添加。</span><span class="sxs-lookup"><span data-stu-id="38332-182">Most of the features jQuery lacks intrinsically can be added with the addition of other libraries.</span></span> <span data-ttu-id="38332-183">但是，SPA 框架（如 Angular）以更集中的方式提供这些功能，因为它从一开始设计的时候就考虑到了这一点。</span><span class="sxs-lookup"><span data-stu-id="38332-183">However, a SPA framework like Angular provides these features in a more integrated fashion, since it's been designed with all of them in mind from the start.</span></span> <span data-ttu-id="38332-184">此外，jQuery 是一种命令性库，这意味着你需要调用 jQuery 函数才能使用 jQuery 执行任何任务。</span><span class="sxs-lookup"><span data-stu-id="38332-184">Also, jQuery is an imperative library, meaning that you need to call jQuery functions in order to do anything with jQuery.</span></span> <span data-ttu-id="38332-185">SPA 框架提供的很多工作和功能都可以声明的方式完成，无需编写任何实际代码。</span><span class="sxs-lookup"><span data-stu-id="38332-185">Much of the work and functionality that SPA frameworks provide can be done declaratively, requiring no actual code to be written.</span></span>

<span data-ttu-id="38332-186">数据绑定便是一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="38332-186">Data binding is a great example of this.</span></span> <span data-ttu-id="38332-187">在 jQuery 中，通常只需要一个代码行就能获得 DOM 元素的值或设置某元素的值。</span><span class="sxs-lookup"><span data-stu-id="38332-187">In jQuery, it usually only takes one line of code to get the value of a DOM element or to set an element's value.</span></span> <span data-ttu-id="38332-188">但是，一旦需要更改元素值就需要编写此行代码，有时这会出现在一个页面上的多个函数中。</span><span class="sxs-lookup"><span data-stu-id="38332-188">However, you have to write this code anytime you need to change the value of the element, and sometimes this will occur in multiple functions on a page.</span></span> <span data-ttu-id="38332-189">另一常见示例是元素可见性。</span><span class="sxs-lookup"><span data-stu-id="38332-189">Another common example is element visibility.</span></span> <span data-ttu-id="38332-190">在 jQuery 中，可能需要在很多位置编写代码来控制特定元素是否可见。</span><span class="sxs-lookup"><span data-stu-id="38332-190">In jQuery, there might be many different places where you'd write code to control whether certain elements were visible.</span></span> <span data-ttu-id="38332-191">每这两种情况中，如果使用数据绑定，便无需编写任何代码。</span><span class="sxs-lookup"><span data-stu-id="38332-191">In each of these cases, when using data binding, no code would need to be written.</span></span> <span data-ttu-id="38332-192">只需将相关元素的值或可见性绑定到页面上的 viewmodel 即可，对该 viewmodel 的任何更改都会自动反映在绑定的元素中  。</span><span class="sxs-lookup"><span data-stu-id="38332-192">You'd simply bind the value or visibility of the elements in question to a *viewmodel* on the page, and changes to that viewmodel would automatically be reflected in the bound elements.</span></span>

### <a name="angular-spas"></a><span data-ttu-id="38332-193">Angular SPA</span><span class="sxs-lookup"><span data-stu-id="38332-193">Angular SPAs</span></span>

<span data-ttu-id="38332-194">Angular 仍是世界上最常用的一种 JavaScript 框架。</span><span class="sxs-lookup"><span data-stu-id="38332-194">Angular remains one of the world's most popular JavaScript frameworks.</span></span> <span data-ttu-id="38332-195">从 Angular 2 开始，团队彻底重建了框架（使用 [TypeScript](https://www.typescriptlang.org/)），并从最初的 AngularJS 名称重新命名为简单的 Angular。</span><span class="sxs-lookup"><span data-stu-id="38332-195">Since Angular 2, the team rebuilt the framework from the ground up (using [TypeScript](https://www.typescriptlang.org/)) and rebranded from the original AngularJS name to simply Angular.</span></span> <span data-ttu-id="38332-196">经过数年的发展，重新设计的 Angular 仍是用于生成单页应用程序的可靠框架。</span><span class="sxs-lookup"><span data-stu-id="38332-196">Now several years old, the redesigned Angular continues to be a robust framework for building Single Page Applications.</span></span>

<span data-ttu-id="38332-197">Angular 应用程序基于组件构建。</span><span class="sxs-lookup"><span data-stu-id="38332-197">Angular applications are built from components.</span></span> <span data-ttu-id="38332-198">组件通过特殊对象与 HTML 模板进行组合，并控制页面的一部分。</span><span class="sxs-lookup"><span data-stu-id="38332-198">Components combine HTML templates with special objects and control a portion of the page.</span></span> <span data-ttu-id="38332-199">下面是 Angular 文档中的简单组件：</span><span class="sxs-lookup"><span data-stu-id="38332-199">A simple component from Angular's docs is shown here:</span></span>

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

<span data-ttu-id="38332-200">组件使用 @Component 修饰器函数定义，可接收有关组件的元数据。</span><span class="sxs-lookup"><span data-stu-id="38332-200">Components are defined using the @Component decorator function, which takes in metadata about the component.</span></span> <span data-ttu-id="38332-201">选择器属性可在显示此组件的页面上标识元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="38332-201">The selector property identifies the ID of the element on the page where this component will be displayed.</span></span> <span data-ttu-id="38332-202">模板属性是一个简单的 HTML 模板，包括最后一行上定义的对应于组件名称属性的占位符。</span><span class="sxs-lookup"><span data-stu-id="38332-202">The template property is a simple HTML template that includes a placeholder that corresponds to the component's name property, defined on the last line.</span></span>

<span data-ttu-id="38332-203">通过使用组件和模板，而不是 DOM 元素，Angular 应用可以更高的抽象级别操作，且比单独使用 JavaScript（也称为“vanilla JS”）或 jQuery 编写的应用具有更少的总体代码。</span><span class="sxs-lookup"><span data-stu-id="38332-203">By working with components and templates, instead of DOM elements, Angular apps can operate at a higher level of abstraction and with less overall code than apps written using just JavaScript (also called "vanilla JS") or with jQuery.</span></span> <span data-ttu-id="38332-204">Angular 还强加了有关如何组织客户端脚本文件的特定顺序。</span><span class="sxs-lookup"><span data-stu-id="38332-204">Angular also imposes some order on how you organize your client-side script files.</span></span> <span data-ttu-id="38332-205">按照约定，Angular 应用使用常用文件夹结构，同时模块和组件脚本文件位于应用文件夹中。</span><span class="sxs-lookup"><span data-stu-id="38332-205">By convention, Angular apps use a common folder structure, with module and component script files located in an app folder.</span></span> <span data-ttu-id="38332-206">与生成、部署和测试应用相关的 Angular 脚本通常位于更高级别的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="38332-206">Angular scripts concerned with building, deploying, and testing the app are typically located in a higher-level folder.</span></span>

<span data-ttu-id="38332-207">可以使用 CLI 开发 Angular 应用。</span><span class="sxs-lookup"><span data-stu-id="38332-207">You can develop Angular apps by using a CLI.</span></span> <span data-ttu-id="38332-208">从本地入门 Angular 开发（假设已安装 git 和 npm）包括简单地从 GitHub 中克隆存储库以及运行 `npm install` 和 `npm start`。</span><span class="sxs-lookup"><span data-stu-id="38332-208">Getting started with Angular development locally (assuming you already have git and npm installed) consists of simply cloning a repo from GitHub and running `npm install` and `npm start`.</span></span> <span data-ttu-id="38332-209">除此之外，Angular 附带自己的 CLI，可用于创建项目、添加工具，并协助测试、打包和部署任务。</span><span class="sxs-lookup"><span data-stu-id="38332-209">Beyond this, Angular ships its own CLI, which can create projects, add files, and assist with testing, bundling, and deployment tasks.</span></span> <span data-ttu-id="38332-210">这种 CLI 友好性也使 Angular 特别兼容 ASP.NET Core，后者也可提供很好的 CLI 支持。</span><span class="sxs-lookup"><span data-stu-id="38332-210">This CLI friendliness makes Angular especially compatible with ASP.NET Core, which also features great CLI support.</span></span>

<span data-ttu-id="38332-211">Microsoft 开发了一个参考应用程序，[eShopOnContainers](https://aka.ms/MicroservicesArchitecture)，其中包含 Angular SPA 实现。</span><span class="sxs-lookup"><span data-stu-id="38332-211">Microsoft has developed a reference application, [eShopOnContainers](https://aka.ms/MicroservicesArchitecture), which includes an Angular SPA implementation.</span></span> <span data-ttu-id="38332-212">此应用包含 Angular 模块，可用于管理在线商店的购物篮，加载和显示其目录中的商品并处理订单创建。</span><span class="sxs-lookup"><span data-stu-id="38332-212">This app includes Angular modules to manage the online store's shopping basket, load and display items from its catalog, and handling order creation.</span></span> <span data-ttu-id="38332-213">可以在 [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA) 中查看和下载该示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="38332-213">You can view and download the sample application from [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA).</span></span>

### <a name="react"></a><span data-ttu-id="38332-214">React</span><span class="sxs-lookup"><span data-stu-id="38332-214">React</span></span>

<span data-ttu-id="38332-215">与 Angular 不同，Angular 提供完整的模型 - 视图 - 控制器模式实现，而 React 仅关注视图。</span><span class="sxs-lookup"><span data-stu-id="38332-215">Unlike Angular, which offers a full Model-View-Controller pattern implementation, React is only concerned with views.</span></span> <span data-ttu-id="38332-216">它不是一个框架，只是一个库，因此需要利用其他库才能生成 SPA。</span><span class="sxs-lookup"><span data-stu-id="38332-216">It's not a framework, just a library, so to build a SPA you'll need to leverage additional libraries.</span></span> <span data-ttu-id="38332-217">有许多库旨在与 React 一起使用，以生成丰富的单页应用程序。</span><span class="sxs-lookup"><span data-stu-id="38332-217">There are a number of libraries that are designed to be used with React to produce rich single page applications.</span></span>

<span data-ttu-id="38332-218">React 最重要的特征之一是使用虚拟 DOM。</span><span class="sxs-lookup"><span data-stu-id="38332-218">One of React's most important features is its use of a virtual DOM.</span></span> <span data-ttu-id="38332-219">虚拟 DOM 可向 React 提供多项好处，包括性能（虚拟 DOM 可优化实际 DOM 的哪部分需要更新）和可测试性（无需使用浏览器即可测试 React 和它与虚拟 DOM 的交互）。</span><span class="sxs-lookup"><span data-stu-id="38332-219">The virtual DOM provides React with several advantages, including performance (the virtual DOM can optimize which parts of the actual DOM need to be updated) and testability (no need to have a browser to test React and its interactions with its virtual DOM).</span></span>

<span data-ttu-id="38332-220">React 很少使用与 HTML 配合的方式。</span><span class="sxs-lookup"><span data-stu-id="38332-220">React is also unusual in how it works with HTML.</span></span> <span data-ttu-id="38332-221">React 直接在其 JavaScript 代码中以 JSX 的形式添加 HTML，而没有代码和标记（可能引用 HTML 属性中出现的 JavaScript）之间的严格分离。</span><span class="sxs-lookup"><span data-stu-id="38332-221">Rather than having a strict separation between code and markup (with references to JavaScript appearing in HTML attributes perhaps), React adds HTML directly within its JavaScript code as JSX.</span></span> <span data-ttu-id="38332-222">JSX 是类似 HTML 的语法，可向下编译为纯 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="38332-222">JSX is HTML-like syntax that can compile down to pure JavaScript.</span></span> <span data-ttu-id="38332-223">例如：</span><span class="sxs-lookup"><span data-stu-id="38332-223">For example:</span></span>

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

<span data-ttu-id="38332-224">如果已了解 JavaScript，学习 React 应该很简单。</span><span class="sxs-lookup"><span data-stu-id="38332-224">If you already know JavaScript, learning React should be easy.</span></span> <span data-ttu-id="38332-225">与 Angular 或其他常用库相比，它几乎不涉及众多的学习曲线或特殊语法。</span><span class="sxs-lookup"><span data-stu-id="38332-225">There isn't nearly as much learning curve or special syntax involved as with Angular or other popular libraries.</span></span>

<span data-ttu-id="38332-226">由于React 不是完整的框架，因此通常需要其他库来处理路由、Web API 调用和依赖关系管理等任务。</span><span class="sxs-lookup"><span data-stu-id="38332-226">Because React isn't a full framework, you'll typically want other libraries to handle things like routing, web API calls, and dependency management.</span></span> <span data-ttu-id="38332-227">好处是可为每个任务选择最合适的库，但坏处时需要进行所有决策，并在完成后验证所有选定库是否可以很好地协同工作。</span><span class="sxs-lookup"><span data-stu-id="38332-227">The nice thing is, you can pick the best library for each of these, but the disadvantage is that you need to make all of these decisions and verify all of your chosen libraries work well together when you're done.</span></span> <span data-ttu-id="38332-228">如果想要一个好的开端，可使用初学者工具包（如 React Slingshot）,它可使用 React 预先打包一组可兼容库。</span><span class="sxs-lookup"><span data-stu-id="38332-228">If you want a good starting point, you can use a starter kit like React Slingshot, which prepackages a set of compatible libraries together with React.</span></span>

### <a name="vue"></a><span data-ttu-id="38332-229">Vue</span><span class="sxs-lookup"><span data-stu-id="38332-229">Vue</span></span>

<span data-ttu-id="38332-230">在其入门指南中，“Vue 是用于生成用户界面的渐进式框架。</span><span class="sxs-lookup"><span data-stu-id="38332-230">From its getting started guide, "Vue is a progressive framework for building user interfaces.</span></span> <span data-ttu-id="38332-231">与其他单一框架不同，Vue 旨在从头开始逐渐采用。</span><span class="sxs-lookup"><span data-stu-id="38332-231">Unlike other monolithic frameworks, Vue is designed from the ground up to be incrementally adoptable.</span></span> <span data-ttu-id="38332-232">核心库仅集中在视图层，易于提取并与其他库或现有项目集成。</span><span class="sxs-lookup"><span data-stu-id="38332-232">The core library is focused on the view layer only, and is easy to pick up and integrate with other libraries or existing projects.</span></span> <span data-ttu-id="38332-233">另一方面，与新式工具和支持库结合使用时，Vue 完全有能力为复杂的单页应用程序提供支持。”</span><span class="sxs-lookup"><span data-stu-id="38332-233">On the other hand, Vue is perfectly capable of powering sophisticated Single-Page Applications when used in combination with modern tooling and supporting libraries."</span></span>

<span data-ttu-id="38332-234">开始使用 Vue 只需要在 HTML 文件中包含其脚本：</span><span class="sxs-lookup"><span data-stu-id="38332-234">Getting started with Vue simply requires including its script within an HTML file:</span></span>

```html
<!-- development version, includes helpful console warnings -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

<span data-ttu-id="38332-235">添加了框架之后，你就可以使用 Vue 的简单模板语法以声明方式将数据呈现到 DOM：</span><span class="sxs-lookup"><span data-stu-id="38332-235">With the framework added, you're then able to declaratively render data to the DOM using Vue's straightforward templating syntax:</span></span>

```html
<div id="app">
  {{ message }}
</div>
```

<span data-ttu-id="38332-236">然后添加以下脚本：</span><span class="sxs-lookup"><span data-stu-id="38332-236">and then adding the following script:</span></span>

```js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  }
})
```

<span data-ttu-id="38332-237">这足以在页面上呈现“Hello Vue!”</span><span class="sxs-lookup"><span data-stu-id="38332-237">This is enough to render "Hello Vue!"</span></span> <span data-ttu-id="38332-238">。</span><span class="sxs-lookup"><span data-stu-id="38332-238">on the page.</span></span> <span data-ttu-id="38332-239">但是，请注意，Vue 并不只是将消息呈现给 div 一次。</span><span class="sxs-lookup"><span data-stu-id="38332-239">Note, however, that Vue isn't simply rendering the message to the div once.</span></span> <span data-ttu-id="38332-240">它支持数据绑定和动态更新，因此如果 `message` 的值发生更改，`<div>` 中的值将立即更新以反映更改。</span><span class="sxs-lookup"><span data-stu-id="38332-240">It supports databinding and dynamic updates such that if the value of `message` changes, the value in the `<div>` is immediately updated to reflect it.</span></span>

<span data-ttu-id="38332-241">当然，这里仅介绍 Vue 的简单功能。</span><span class="sxs-lookup"><span data-stu-id="38332-241">Of course, this only scratches the surface of what Vue is capable of.</span></span> <span data-ttu-id="38332-242">在过去的几年中，它非常受欢迎，并且拥有一个庞大的社区。</span><span class="sxs-lookup"><span data-stu-id="38332-242">It's gained a great deal of popularity in the last several years and has a large community.</span></span> <span data-ttu-id="38332-243">有一个[庞大且不断增长的支持组件和库列表](https://github.com/vuejs/awesome-vue#redux)，它们可以与 Vue 一起扩展。</span><span class="sxs-lookup"><span data-stu-id="38332-243">There's a [huge and growing list of supporting components and libraries](https://github.com/vuejs/awesome-vue#redux) that work with Vue to extend it as well.</span></span> <span data-ttu-id="38332-244">如果希望将客户端行为添加到 Web 应用程序中，或者正在考虑生成完整的 SPA，那么值得对 Vue 进行一番研究。</span><span class="sxs-lookup"><span data-stu-id="38332-244">If you're looking to add client-side behavior to your web application or considering building a full SPA, Vue is worth investigating.</span></span>

### <a name="choosing-a-spa-framework"></a><span data-ttu-id="38332-245">选择 SPA 框架</span><span class="sxs-lookup"><span data-stu-id="38332-245">Choosing a SPA Framework</span></span>

<span data-ttu-id="38332-246">考虑哪个 JavaScript 框架最适合支持 SPA 时，请注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="38332-246">When considering which JavaScript framework will work best to support your SPA, keep in mind the following considerations:</span></span>

- <span data-ttu-id="38332-247">团队是否熟悉该框架及其依赖关系（某些情况下还包括 TypeScript）？</span><span class="sxs-lookup"><span data-stu-id="38332-247">Is your team familiar with the framework and its dependencies (including TypeScript in some cases)?</span></span>

- <span data-ttu-id="38332-248">框架的“固执”程度如何，以及是否同意它处理事情的默认方式？</span><span class="sxs-lookup"><span data-stu-id="38332-248">How opinionated is the framework, and do you agree with its default way of doing things?</span></span>

- <span data-ttu-id="38332-249">它（或伴随库）是否包括应用需要的所有功能？</span><span class="sxs-lookup"><span data-stu-id="38332-249">Does it (or a companion library) include all of the features your app requires?</span></span>

- <span data-ttu-id="38332-250">是否有详细的文档记录？</span><span class="sxs-lookup"><span data-stu-id="38332-250">Is it well documented?</span></span>

- <span data-ttu-id="38332-251">它在社区中的活跃程度？</span><span class="sxs-lookup"><span data-stu-id="38332-251">How active is its community?</span></span> <span data-ttu-id="38332-252">新项目是否使用它生成？</span><span class="sxs-lookup"><span data-stu-id="38332-252">Are new projects being built with it?</span></span>

- <span data-ttu-id="38332-253">它的核心团队活跃程度如何？</span><span class="sxs-lookup"><span data-stu-id="38332-253">How active is its core team?</span></span> <span data-ttu-id="38332-254">是否定期解决问题和发布新版本？</span><span class="sxs-lookup"><span data-stu-id="38332-254">Are issues being resolved and new versions shipped regularly?</span></span>

<span data-ttu-id="38332-255">JavaScript 框架仍以极快的速度发展。</span><span class="sxs-lookup"><span data-stu-id="38332-255">JavaScript frameworks continue to evolve with breakneck speed.</span></span> <span data-ttu-id="38332-256">使用上面列出的注意事项，可帮助减轻选择之后会后悔依赖的框架的风险。</span><span class="sxs-lookup"><span data-stu-id="38332-256">Use the considerations listed above to help mitigate the risk of choosing a framework you'll later regret being dependent upon.</span></span> <span data-ttu-id="38332-257">如果你特别不愿意承担风险，请考虑提供商业支持和/或大型企业开发的框架。</span><span class="sxs-lookup"><span data-stu-id="38332-257">If you're particularly risk-averse, consider a framework that offers commercial support and/or is being developed by a large enterprise.</span></span>

> ### <a name="references--client-web-technologies"></a><span data-ttu-id="38332-258">参考 - 客户端 Web 技术</span><span class="sxs-lookup"><span data-stu-id="38332-258">References – Client Web Technologies</span></span>
>
> - <span data-ttu-id="38332-259">**HTML 和 CSS**</span><span class="sxs-lookup"><span data-stu-id="38332-259">**HTML and CSS**</span></span>  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - <span data-ttu-id="38332-260">**Sass 与 LESS**</span><span class="sxs-lookup"><span data-stu-id="38332-260">**Sass vs. LESS**</span></span>  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - <span data-ttu-id="38332-261">**使用 LESS、Sass 和 Font Awesome 为 ASP.NET Core 应用设置样式**</span><span class="sxs-lookup"><span data-stu-id="38332-261">**Styling ASP.NET Core Apps with LESS, Sass, and Font Awesome**</span></span>  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - <span data-ttu-id="38332-262">**ASP.NET Core 中的客户端开发**</span><span class="sxs-lookup"><span data-stu-id="38332-262">**Client-Side Development in ASP.NET Core**</span></span>  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - <span data-ttu-id="38332-263">**jQuery**</span><span class="sxs-lookup"><span data-stu-id="38332-263">**jQuery**</span></span>  
> <https://jquery.com/>
> - <span data-ttu-id="38332-264">**jQuery 与 AngularJS**</span><span class="sxs-lookup"><span data-stu-id="38332-264">**jQuery vs AngularJS**</span></span>  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - <span data-ttu-id="38332-265">**Angular**</span><span class="sxs-lookup"><span data-stu-id="38332-265">**Angular**</span></span>  
> <https://angular.io/>
> - <span data-ttu-id="38332-266">**React**</span><span class="sxs-lookup"><span data-stu-id="38332-266">**React**</span></span>  
> <https://reactjs.org/>
> - <span data-ttu-id="38332-267">**Vue**</span><span class="sxs-lookup"><span data-stu-id="38332-267">**Vue**</span></span>  
> <https://vuejs.org/>
> - <span data-ttu-id="38332-268">**Angular、React 与 Vue：2020 年要选择哪种框架**
> <https://www.codeinwp.com/blog/angular-vs-vue-vs-react/></span><span class="sxs-lookup"><span data-stu-id="38332-268">**Angular vs React vs Vue: Which Framework to Choose in 2020**
<https://www.codeinwp.com/blog/angular-vs-vue-vs-react/></span></span>
> - <span data-ttu-id="38332-269">**2020 年用于前端开发的顶级 JavaScript 框架**</span><span class="sxs-lookup"><span data-stu-id="38332-269">**The Top JavaScript Frameworks for Front-End Development in 2020**</span></span>  
> <https://www.freecodecamp.org/news/complete-guide-for-front-end-developers-javascript-frameworks-2019/>

>[!div class="step-by-step"]
><span data-ttu-id="38332-270">[上一页](common-web-application-architectures.md)
>[下一页](develop-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="38332-270">[Previous](common-web-application-architectures.md)
[Next](develop-asp-net-core-mvc-apps.md)</span></span>
