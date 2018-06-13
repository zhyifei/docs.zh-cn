---
title: 正则表达式示例
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee4d884a0efbeb6e57ed727396bf3bcb39979774
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172498"
---
# <a name="regular-expression-examples"></a><span data-ttu-id="17227-102">正则表达式示例</span><span class="sxs-lookup"><span data-stu-id="17227-102">Regular Expression Examples</span></span>
<span data-ttu-id="17227-103">此部分包含说明如何在常见应用程序中使用正则表达式的代码示例。</span><span class="sxs-lookup"><span data-stu-id="17227-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17227-104"><xref:System.Web.RegularExpressions> 命名空间包含大量正则表达式对象，这些对象实现预定义的正则表达式模式，用于分析 HTML、XML 和 ASP.NET 文档中的字符串。</span><span class="sxs-lookup"><span data-stu-id="17227-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="17227-105">例如，<xref:System.Web.RegularExpressions.TagRegex> 类标识字符串中的开始标记，<xref:System.Web.RegularExpressions.CommentRegex> 类标识字符串中的 ASP.NET 注释。</span><span class="sxs-lookup"><span data-stu-id="17227-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17227-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="17227-106">In This Section</span></span>  
 [<span data-ttu-id="17227-107">示例：扫描搜索 HREF</span><span class="sxs-lookup"><span data-stu-id="17227-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="17227-108">收录了搜索输入字符串并打印输出所有 href="…" 值及其在字符串中位置的示例。</span><span class="sxs-lookup"><span data-stu-id="17227-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="17227-109">示例：更改日期格式</span><span class="sxs-lookup"><span data-stu-id="17227-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="17227-110">收录了将格式为 mm/dd/yy 的日期替换为格式为 dd-mm-yy 的日期的示例。</span><span class="sxs-lookup"><span data-stu-id="17227-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="17227-111">如何：从 URL 中提取协议和端口号</span><span class="sxs-lookup"><span data-stu-id="17227-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="17227-112">收录了从包含 URL 的字符串中提取协议和端口号的示例。</span><span class="sxs-lookup"><span data-stu-id="17227-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="17227-113">例如，“http://www.contoso.com:8080/letters/readme.html”返回“http:8080”。</span><span class="sxs-lookup"><span data-stu-id="17227-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="17227-114">如何：从字符串中剥离无效字符</span><span class="sxs-lookup"><span data-stu-id="17227-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="17227-115">收录了从字符串中剥离无效的非字母数字字符的示例。</span><span class="sxs-lookup"><span data-stu-id="17227-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="17227-116">如何：确认字符串是否是有效的电子邮件地址格式</span><span class="sxs-lookup"><span data-stu-id="17227-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="17227-117">提供验证一个字符串是否为有效的电子邮件格式的示例。</span><span class="sxs-lookup"><span data-stu-id="17227-117">Provides an example that verifies that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="17227-118">参考</span><span class="sxs-lookup"><span data-stu-id="17227-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="17227-119">提供了 .NET System.Text.RegularExpressions 命名空间的类库参考信息。</span><span class="sxs-lookup"><span data-stu-id="17227-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="17227-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="17227-120">Related Sections</span></span>  
 [<span data-ttu-id="17227-121">.NET 正则表达式</span><span class="sxs-lookup"><span data-stu-id="17227-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="17227-122">提供正则表达式的编程语言方面的概述。</span><span class="sxs-lookup"><span data-stu-id="17227-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="17227-123">正则表达式对象模型</span><span class="sxs-lookup"><span data-stu-id="17227-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="17227-124">介绍了 `System.Text.RegularExpression` 命名空间中包含的正则表达式类，并收录了用法示例。</span><span class="sxs-lookup"><span data-stu-id="17227-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="17227-125">正则表达式行为的详细信息</span><span class="sxs-lookup"><span data-stu-id="17227-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="17227-126">介绍了 .NET 正则表达式的功能和行为。</span><span class="sxs-lookup"><span data-stu-id="17227-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="17227-127">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="17227-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="17227-128">提供有关可用来定义正则表达式的字符集、运算符和构造的信息。</span><span class="sxs-lookup"><span data-stu-id="17227-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
