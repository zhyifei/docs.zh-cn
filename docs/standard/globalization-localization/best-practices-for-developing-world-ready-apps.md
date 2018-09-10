---
title: 开发全球通用应用程序的最佳做法
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- global applications, best practices
- world-ready applications, best practices
- globalization [.NET Framework], best practices
- international applications [.NET Framework], best practices
ms.assetid: f08169c7-aad8-4ec3-9a21-9ebd3b89986c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35b8e062c9f207eba19bcee5593425095de2e267
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041465"
---
# <a name="best-practices-for-developing-world-ready-applications"></a><span data-ttu-id="9ec67-102">开发全球通用应用程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="9ec67-102">Best Practices for Developing World-Ready Applications</span></span>
<span data-ttu-id="9ec67-103">本节描述在开发全球通用的应用程序时应遵循的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="9ec67-103">This section describes the best practices to follow when developing world-ready applications.</span></span>  
  
## <a name="globalization-best-practices"></a><span data-ttu-id="9ec67-104">全球化最佳做法</span><span class="sxs-lookup"><span data-stu-id="9ec67-104">Globalization Best Practices</span></span>  
  
1.  <span data-ttu-id="9ec67-105">在内部使应用程序代码成为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="9ec67-105">Make your application Unicode internally.</span></span>  
  
2.  <span data-ttu-id="9ec67-106">使用 <xref:System.Globalization> 命名空间提供的区域性识别类来操作和格式化数据。</span><span class="sxs-lookup"><span data-stu-id="9ec67-106">Use the culture-aware classes provided by the <xref:System.Globalization> namespace to manipulate and format data.</span></span>  
  
    -   <span data-ttu-id="9ec67-107">对于排序，使用 <xref:System.Globalization.SortKey> 类和 <xref:System.Globalization.CompareInfo> 类。</span><span class="sxs-lookup"><span data-stu-id="9ec67-107">For sorting, use the <xref:System.Globalization.SortKey> class and the <xref:System.Globalization.CompareInfo> class.</span></span>  
  
    -   <span data-ttu-id="9ec67-108">对于字符串比较，使用 <xref:System.Globalization.CompareInfo> 类。</span><span class="sxs-lookup"><span data-stu-id="9ec67-108">For string comparisons, use the <xref:System.Globalization.CompareInfo> class.</span></span>  
  
    -   <span data-ttu-id="9ec67-109">对于日期和时间格式化，使用 <xref:System.Globalization.DateTimeFormatInfo> 类。</span><span class="sxs-lookup"><span data-stu-id="9ec67-109">For date and time formatting, use the <xref:System.Globalization.DateTimeFormatInfo> class.</span></span>  
  
    -   <span data-ttu-id="9ec67-110">对于数字格式化，使用 <xref:System.Globalization.NumberFormatInfo> 类。</span><span class="sxs-lookup"><span data-stu-id="9ec67-110">For numeric formatting, use the <xref:System.Globalization.NumberFormatInfo> class.</span></span>  
  
    -   <span data-ttu-id="9ec67-111">对于公历和非公历，使用 <xref:System.Globalization.Calendar> 类或特定的日历实现之一。</span><span class="sxs-lookup"><span data-stu-id="9ec67-111">For Gregorian and non-Gregorian calendars, use the <xref:System.Globalization.Calendar> class or one of the specific calendar implementations.</span></span>  
  
3.  <span data-ttu-id="9ec67-112">在适当的情况下，使用 <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> 类提供的区域性属性设置。</span><span class="sxs-lookup"><span data-stu-id="9ec67-112">Use the culture property settings provided by the <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> class in the appropriate situations.</span></span> <span data-ttu-id="9ec67-113">使用 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> 属性来执行格式化任务，如日期和时间或数字的格式化。</span><span class="sxs-lookup"><span data-stu-id="9ec67-113">Use the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> property for formatting tasks, such as date and time or numeric formatting.</span></span> <span data-ttu-id="9ec67-114">使用 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> 属性来检索资源。</span><span class="sxs-lookup"><span data-stu-id="9ec67-114">Use the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property to retrieve resources.</span></span> <span data-ttu-id="9ec67-115">请注意，`CurrentCulture` 和 `CurrentUICulture` 属性可以通过线程进行设置。</span><span class="sxs-lookup"><span data-stu-id="9ec67-115">Note that the `CurrentCulture` and `CurrentUICulture` properties can be set per thread.</span></span>  
  
4.  <span data-ttu-id="9ec67-116">通过使用 <xref:System.Text> 命名空间中的编码类，使应用程序能够与各种编码相互进行数据读写。</span><span class="sxs-lookup"><span data-stu-id="9ec67-116">Enable your application to read and write data to and from a variety of encodings by using the encoding classes in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="9ec67-117">不要采用 ASCII 数据。</span><span class="sxs-lookup"><span data-stu-id="9ec67-117">Do not assume ASCII data.</span></span> <span data-ttu-id="9ec67-118">假定在用户可以输入文本的任何位置都将提供国际字符。</span><span class="sxs-lookup"><span data-stu-id="9ec67-118">Assume that international characters will be supplied anywhere a user can enter text.</span></span> <span data-ttu-id="9ec67-119">例如，应用程序应接受服务器名、目录、文件名、用户名和 URL 中的国际字符。</span><span class="sxs-lookup"><span data-stu-id="9ec67-119">For example, the application should accept international characters in server names, directories, file names, user names, and URLs.</span></span>  
  
5.  <span data-ttu-id="9ec67-120">使用 <xref:System.Text.UTF8Encoding> 类时，出于安全原因，应使用此类提供的错误检测功能。</span><span class="sxs-lookup"><span data-stu-id="9ec67-120">When using the <xref:System.Text.UTF8Encoding> class, for security reasons, use the error detection feature offered by this class.</span></span> <span data-ttu-id="9ec67-121">为了打开错误检测功能，应用程序会使用具有一个 `throwOnInvalidBytes` 参数的构造函数来创建该类的一个实例，并将该参数的值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="9ec67-121">To turn on the error detection feature, the application creates an instance of the class using the constructor that takes a `throwOnInvalidBytes` parameter and sets the value of this parameter to `true`.</span></span>  
  
6.  <span data-ttu-id="9ec67-122">尽可能将字符串按整个字符串处理，而不是按一系列个别字符处理。</span><span class="sxs-lookup"><span data-stu-id="9ec67-122">Whenever possible, handle strings as entire strings instead of as a series of individual characters.</span></span> <span data-ttu-id="9ec67-123">这在排序或搜索子字符串时尤为重要。</span><span class="sxs-lookup"><span data-stu-id="9ec67-123">This is especially important when sorting or searching for substrings.</span></span> <span data-ttu-id="9ec67-124">这可以防止与分析组合字符有关的问题。</span><span class="sxs-lookup"><span data-stu-id="9ec67-124">This will prevent problems associated with parsing combined characters.</span></span>  
  
7.  <span data-ttu-id="9ec67-125">使用 <xref:System.Drawing> 命名空间提供的类来显示文本。</span><span class="sxs-lookup"><span data-stu-id="9ec67-125">Display text using the classes provided by the <xref:System.Drawing> namespace.</span></span>  
  
8.  <span data-ttu-id="9ec67-126">为保持操作系统间的一致性，不要允许用户设置重写 <xref:System.Globalization.CultureInfo>。</span><span class="sxs-lookup"><span data-stu-id="9ec67-126">For consistency across operating systems, do not allow user settings to override <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="9ec67-127">使用接受 `CultureInfo` 参数的 `useUserOverride` 构造函数并将此参数设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="9ec67-127">Use the `CultureInfo` constructor that accepts a `useUserOverride` parameter and set it to `false`.</span></span>  
  
9. <span data-ttu-id="9ec67-128">在国际操作系统版本上使用国际数据来测试应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="9ec67-128">Test your application functionality on international operating system versions, using international data.</span></span>  
  
10. <span data-ttu-id="9ec67-129">如果安全决策基于字符串比较或大小写更改操作的结果，请让应用程序执行不区分区域性的操作。</span><span class="sxs-lookup"><span data-stu-id="9ec67-129">If a security decision is based on the result of a string comparison or case change operation, have the application perform a culture-insensitive operation.</span></span> <span data-ttu-id="9ec67-130">这种做法可确保结果不会受 `CultureInfo.CurrentCulture` 值的影响。</span><span class="sxs-lookup"><span data-stu-id="9ec67-130">This practice ensures that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="9ec67-131">有关展示了区域性敏感型字符串比较如何产生不一致结果的示例，请参阅[字符串使用最佳做法](../../../docs/standard/base-types/best-practices-strings.md)的“使用当前区域性的字符串比较”部分。</span><span class="sxs-lookup"><span data-stu-id="9ec67-131">See the "String Comparisons that Use the Current Culture" section of [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) for an example that demonstrates how culture-sensitive string comparisons can produce inconsistent results.</span></span>  
  
## <a name="localization-best-practices"></a><span data-ttu-id="9ec67-132">本地化最佳做法</span><span class="sxs-lookup"><span data-stu-id="9ec67-132">Localization Best Practices</span></span>  
  
1.  <span data-ttu-id="9ec67-133">将所有可本地化的资源移动到单独的纯资源 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="9ec67-133">Move all localizable resources to separate resource-only DLLs.</span></span> <span data-ttu-id="9ec67-134">可本地化的资源包括用户界面元素，如字符串、错误消息、对话框、菜单以及嵌入的对象资源。</span><span class="sxs-lookup"><span data-stu-id="9ec67-134">Localizable resources include user interface elements, such as strings, error messages, dialog boxes, menus, and embedded object resources.</span></span>  
  
2.  <span data-ttu-id="9ec67-135">不要对字符串或用户界面资源进行硬编码。</span><span class="sxs-lookup"><span data-stu-id="9ec67-135">Do not hardcode strings or user interface resources.</span></span>  
  
3.  <span data-ttu-id="9ec67-136">不要将不可本地化的资源放在纯资源 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="9ec67-136">Do not put nonlocalizable resources into the resource-only DLLs.</span></span> <span data-ttu-id="9ec67-137">否则会使翻译人员产生困惑。</span><span class="sxs-lookup"><span data-stu-id="9ec67-137">This causes confusion for translators.</span></span>  
  
4.  <span data-ttu-id="9ec67-138">不要使用在运行时从串联词组生成的复合字符串。</span><span class="sxs-lookup"><span data-stu-id="9ec67-138">Do not use composite strings that are built at run time from concatenated phrases.</span></span> <span data-ttu-id="9ec67-139">复合字符串难以本地化，因为它们往往采用英语语法顺序，而此顺序并不适用于所有语言。</span><span class="sxs-lookup"><span data-stu-id="9ec67-139">Composite strings are difficult to localize because they often assume an English grammatical order that does not apply to all languages.</span></span>  
  
5.  <span data-ttu-id="9ec67-140">避免不明确的结构，如“Empty Folder”，因为根据字符串组成部分的语法规则，这些字符串可能产生不同的翻译。</span><span class="sxs-lookup"><span data-stu-id="9ec67-140">Avoid ambiguous constructs such as "Empty Folder" where the strings can be translated differently depending on the grammatical roles of the string components.</span></span> <span data-ttu-id="9ec67-141">例如，“empty”既可以是一个动词，也可以是一个形容词，因此在诸如意大利语或法语等语言中就可能导致不同的翻译。</span><span class="sxs-lookup"><span data-stu-id="9ec67-141">For example, "empty" can be either a verb or an adjective, which can lead to different translations in languages such as Italian or French.</span></span>  
  
6.  <span data-ttu-id="9ec67-142">避免在应用程序中使用包含文本的图像和图标。</span><span class="sxs-lookup"><span data-stu-id="9ec67-142">Avoid using images and icons that contain text in your application.</span></span> <span data-ttu-id="9ec67-143">本地化这些图像和图标的成本是很大的。</span><span class="sxs-lookup"><span data-stu-id="9ec67-143">They are expensive to localize.</span></span>  
  
7.  <span data-ttu-id="9ec67-144">允许在用户界面中为字符串长度的扩展保留足够的空间。</span><span class="sxs-lookup"><span data-stu-id="9ec67-144">Allow plenty of room for the length of strings to expand in the user interface.</span></span> <span data-ttu-id="9ec67-145">在某些语言中，词组所需的空间可能比在其他语言中多 50-75%。</span><span class="sxs-lookup"><span data-stu-id="9ec67-145">In some languages, phrases can require 50-75 percent more space than they need in other languages.</span></span>  
  
8.  <span data-ttu-id="9ec67-146">使用 <xref:System.Resources.ResourceManager?displayProperty=nameWithType> 类来根据区域性检索资源。</span><span class="sxs-lookup"><span data-stu-id="9ec67-146">Use the <xref:System.Resources.ResourceManager?displayProperty=nameWithType> class to retrieve resources based on culture.</span></span>  
  
9. <span data-ttu-id="9ec67-147">使用 Visual Studio 创建 Windows 窗体对话框，以便可以使用 [Windows 窗体资源编辑器 (Winres.exe)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md) 对它们进行本地化。</span><span class="sxs-lookup"><span data-stu-id="9ec67-147">Use Visual Studio to create Windows Forms dialog boxes, so that they can be localized using the [Windows Forms Resource Editor (Winres.exe)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span> <span data-ttu-id="9ec67-148">不要对 Windows 窗体对话框进行手动编码。</span><span class="sxs-lookup"><span data-stu-id="9ec67-148">Do not code Windows Forms dialog boxes by hand.</span></span>  
  
10. <span data-ttu-id="9ec67-149">安排进行专业本地化工作（翻译）。</span><span class="sxs-lookup"><span data-stu-id="9ec67-149">Arrange for professional localization (translation).</span></span>  
  
11. <span data-ttu-id="9ec67-150">有关创建并本地化资源的完整说明，请参阅[应用中的资源](../../../docs/framework/resources/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec67-150">For a complete description of creating and localizing resources, see [Resources in Applications](../../../docs/framework/resources/index.md).</span></span>  
  
## <a name="globalization-best-practices-for-aspnet-applications"></a><span data-ttu-id="9ec67-151">ASP.NET 应用程序的全球化最佳做法</span><span class="sxs-lookup"><span data-stu-id="9ec67-151">Globalization Best Practices for ASP.NET Applications</span></span>  
  
1.  <span data-ttu-id="9ec67-152">在应用程序中显式设置 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> 和 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="9ec67-152">Explicitly set the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> and <xref:System.Globalization.CultureInfo.CurrentCulture%2A> properties in your application.</span></span> <span data-ttu-id="9ec67-153">不要依赖于默认设置。</span><span class="sxs-lookup"><span data-stu-id="9ec67-153">Do not rely on defaults.</span></span>  
  
2.  <span data-ttu-id="9ec67-154">请注意，ASP.NET 应用程序是托管应用程序，因此可以使用与其他托管应用程序相同的类，以根据区域性检索、显示和操作信息。</span><span class="sxs-lookup"><span data-stu-id="9ec67-154">Note that ASP.NET applications are managed applications and therefore can use the same classes as other managed applications for retrieving, displaying, and manipulating information based on culture.</span></span>  
  
3.  <span data-ttu-id="9ec67-155">注意在 ASP.NET 中可以指定以下三种编码类型：</span><span class="sxs-lookup"><span data-stu-id="9ec67-155">Be aware that you can specify the following three types of encodings in ASP.NET:</span></span>  
  
    -   <span data-ttu-id="9ec67-156">requestEncoding 指定从客户端浏览器接收的编码。</span><span class="sxs-lookup"><span data-stu-id="9ec67-156">requestEncoding specifies the encoding received from the client's browser.</span></span>  
  
    -   <span data-ttu-id="9ec67-157">responseEncoding 指定要发送到客户端浏览器的编码。</span><span class="sxs-lookup"><span data-stu-id="9ec67-157">responseEncoding specifies the encoding to send to the client browser.</span></span> <span data-ttu-id="9ec67-158">在大多数情形下，此编码应该与为 requestEncoding 指定的编码相同。</span><span class="sxs-lookup"><span data-stu-id="9ec67-158">In most situations, this encoding should be the same as that specified for requestEncoding.</span></span>  
  
    -   <span data-ttu-id="9ec67-159">fileEncoding 指定用于 .aspx、.asmx 和 .asax 文件分析的默认编码。</span><span class="sxs-lookup"><span data-stu-id="9ec67-159">fileEncoding specifies the default encoding for .aspx, .asmx, and .asax file parsing.</span></span>  
  
4.  <span data-ttu-id="9ec67-160">在 ASP.NET 应用程序中的以下三个位置指定 requestEncoding、responseEncoding、fileEncoding、culture 和 uiCulture 特性的值：</span><span class="sxs-lookup"><span data-stu-id="9ec67-160">Specify the values for the requestEncoding, responseEncoding, fileEncoding, culture, and uiCulture attributes in the following three places in an ASP.NET application:</span></span>  
  
    -   <span data-ttu-id="9ec67-161">在 Web.config 文件的全球化一节中。</span><span class="sxs-lookup"><span data-stu-id="9ec67-161">In the globalization section of a Web.config file.</span></span> <span data-ttu-id="9ec67-162">此文件是 ASP.NET 应用程序的外部文件。</span><span class="sxs-lookup"><span data-stu-id="9ec67-162">This file is external to the ASP.NET application.</span></span> <span data-ttu-id="9ec67-163">有关详细信息，请参阅 [\<globalization> 元素](https://msdn.microsoft.com/library/e2dffc8e-ebd2-439b-a2fd-e3ac5e620da7)。</span><span class="sxs-lookup"><span data-stu-id="9ec67-163">For more information, see [\<globalization> Element](https://msdn.microsoft.com/library/e2dffc8e-ebd2-439b-a2fd-e3ac5e620da7).</span></span>  
  
    -   <span data-ttu-id="9ec67-164">在页面指令中。</span><span class="sxs-lookup"><span data-stu-id="9ec67-164">In a page directive.</span></span> <span data-ttu-id="9ec67-165">请注意，当应用程序在页面中时，文件已经被读取。</span><span class="sxs-lookup"><span data-stu-id="9ec67-165">Note that, when an application is in a page, the file has already been read.</span></span> <span data-ttu-id="9ec67-166">因此，指定 fileEncoding 和 requestEncoding 为时已晚。</span><span class="sxs-lookup"><span data-stu-id="9ec67-166">Therefore, it is too late to specify fileEncoding and requestEncoding.</span></span> <span data-ttu-id="9ec67-167">只有 uiCulture、Culture 和 responseEncoding 可以在页面指令中指定。</span><span class="sxs-lookup"><span data-stu-id="9ec67-167">Only uiCulture, Culture, and responseEncoding can be specified in a page directive.</span></span>  
  
    -   <span data-ttu-id="9ec67-168">在应用程序代码中以编程方式指定。</span><span class="sxs-lookup"><span data-stu-id="9ec67-168">Programmatically in application code.</span></span> <span data-ttu-id="9ec67-169">该设置可能随请求的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="9ec67-169">This setting can vary per request.</span></span> <span data-ttu-id="9ec67-170">同页面指令一样，到打开应用程序代码时，指定 fileEncoding 和 requestEncoding 为时已晚。</span><span class="sxs-lookup"><span data-stu-id="9ec67-170">As with a page directive, by the time the application's code is reached it is too late to specify fileEncoding and requestEncoding.</span></span> <span data-ttu-id="9ec67-171">只有 uiCulture、Culture 和 responseEncoding 可以在应用程序代码中指定。</span><span class="sxs-lookup"><span data-stu-id="9ec67-171">Only uiCulture, Culture, and responseEncoding can be specified in application code.</span></span>  
  
5.  <span data-ttu-id="9ec67-172">请注意，uiCulture 值可以设置为浏览器接受的语言。</span><span class="sxs-lookup"><span data-stu-id="9ec67-172">Note that the uiCulture value can be set to the browser accept language.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec67-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ec67-173">See also</span></span>

- [<span data-ttu-id="9ec67-174">全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="9ec67-174">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
- [<span data-ttu-id="9ec67-175">桌面应用中的资源</span><span class="sxs-lookup"><span data-stu-id="9ec67-175">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
