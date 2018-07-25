---
title: 大小写约定
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ef7913a2601c3a791cb028b4074ce37b9e9421b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575279"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="89330-102">大小写约定</span><span class="sxs-lookup"><span data-stu-id="89330-102">Capitalization Conventions</span></span>
<span data-ttu-id="89330-103">本章中的准则列出了一种针对用例的简单方法，当统一应用此方法时，可以使类型、成员和参数的标识符易于阅读。</span><span class="sxs-lookup"><span data-stu-id="89330-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="89330-104">标识符的大小写规则</span><span class="sxs-lookup"><span data-stu-id="89330-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="89330-105">若要区分标识符中的单词，将在标识符中的每个单词的第一个字母都大写。</span><span class="sxs-lookup"><span data-stu-id="89330-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="89330-106">不使用下划线来区分的单词，或其实，标识符中任意位置。</span><span class="sxs-lookup"><span data-stu-id="89330-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="89330-107">有两种适当的方法，以使其大写标识符，根据使用的标识符：</span><span class="sxs-lookup"><span data-stu-id="89330-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
-   <span data-ttu-id="89330-108">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="89330-108">PascalCasing</span></span>  
  
-   <span data-ttu-id="89330-109">camelcasing 大小写约定</span><span class="sxs-lookup"><span data-stu-id="89330-109">camelCasing</span></span>  
  
 <span data-ttu-id="89330-110">PascalCasing 约定用于除参数名称之外的所有标识符，将每个单词的第一个字符大写（包括超过两个字母的首字母缩写），如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="89330-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="89330-111">这里有一种特殊情况，即遇到两个字母的首字母缩略词时，两个字母都要大写，如下面的标识符所示：</span><span class="sxs-lookup"><span data-stu-id="89330-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="89330-112">camelCasing 约定仅用于参数名称，将除第一个单词之外的每个单词的第一个字符大写，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="89330-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="89330-113">该示例还显示，以 camelCasing 标识符开始的双字母缩写词都是小写的。</span><span class="sxs-lookup"><span data-stu-id="89330-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="89330-114">**✓ 请**将 PascalCasing 用于包含多个单词的所有公共成员、类型和命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="89330-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="89330-115">**✓ 请**将 camelCasing 用于参数名称。</span><span class="sxs-lookup"><span data-stu-id="89330-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="89330-116">下表描述了不同类型的标识符的大小写规则。</span><span class="sxs-lookup"><span data-stu-id="89330-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="89330-117">标识符</span><span class="sxs-lookup"><span data-stu-id="89330-117">Identifier</span></span>|<span data-ttu-id="89330-118">大小写</span><span class="sxs-lookup"><span data-stu-id="89330-118">Casing</span></span>|<span data-ttu-id="89330-119">示例</span><span class="sxs-lookup"><span data-stu-id="89330-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="89330-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="89330-120">Namespace</span></span>|<span data-ttu-id="89330-121">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="89330-122">类型</span><span class="sxs-lookup"><span data-stu-id="89330-122">Type</span></span>|<span data-ttu-id="89330-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="89330-124">接口</span><span class="sxs-lookup"><span data-stu-id="89330-124">Interface</span></span>|<span data-ttu-id="89330-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="89330-126">方法</span><span class="sxs-lookup"><span data-stu-id="89330-126">Method</span></span>|<span data-ttu-id="89330-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="89330-128">属性</span><span class="sxs-lookup"><span data-stu-id="89330-128">Property</span></span>|<span data-ttu-id="89330-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="89330-130">事件</span><span class="sxs-lookup"><span data-stu-id="89330-130">Event</span></span>|<span data-ttu-id="89330-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="89330-132">字段</span><span class="sxs-lookup"><span data-stu-id="89330-132">Field</span></span>|<span data-ttu-id="89330-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="89330-134">枚举值</span><span class="sxs-lookup"><span data-stu-id="89330-134">Enum value</span></span>|<span data-ttu-id="89330-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="89330-136">参数</span><span class="sxs-lookup"><span data-stu-id="89330-136">Parameter</span></span>|<span data-ttu-id="89330-137">Camel</span><span class="sxs-lookup"><span data-stu-id="89330-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="89330-138">利用复合词和常用术语</span><span class="sxs-lookup"><span data-stu-id="89330-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="89330-139">大多数复合字词被视为单个字的大小写的目的。</span><span class="sxs-lookup"><span data-stu-id="89330-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="89330-140">**X 不**利用所谓关闭窗体复合词中的每个单词。</span><span class="sxs-lookup"><span data-stu-id="89330-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="89330-141">这些是编写为单个字词，如终结点的组合词。</span><span class="sxs-lookup"><span data-stu-id="89330-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="89330-142">为了大小写规则，将关闭格式的复合词视为单个单词。</span><span class="sxs-lookup"><span data-stu-id="89330-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="89330-143">使用当前字典来确定是否在关闭窗体中编写的组合词。</span><span class="sxs-lookup"><span data-stu-id="89330-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="89330-144">Pascal</span><span class="sxs-lookup"><span data-stu-id="89330-144">Pascal</span></span>|<span data-ttu-id="89330-145">Camel</span><span class="sxs-lookup"><span data-stu-id="89330-145">Camel</span></span>|<span data-ttu-id="89330-146">不</span><span class="sxs-lookup"><span data-stu-id="89330-146">Not</span></span>|  
|------------|-----------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## <a name="case-sensitivity"></a><span data-ttu-id="89330-147">区分大小写</span><span class="sxs-lookup"><span data-stu-id="89330-147">Case Sensitivity</span></span>  
 <span data-ttu-id="89330-148">可以在 CLR 运行的语言不要求支持区分大小写，尽管某些作用。</span><span class="sxs-lookup"><span data-stu-id="89330-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="89330-149">即使你的语言支持它，不这样做可能会访问你的 framework 的其他语言。</span><span class="sxs-lookup"><span data-stu-id="89330-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="89330-150">因此，任何 Api 时从外部访问，不能依赖于用例单独来区分这两个名称相同的上下文中。</span><span class="sxs-lookup"><span data-stu-id="89330-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="89330-151">**X 不**假定所有编程语言不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="89330-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="89330-152">它们不是。</span><span class="sxs-lookup"><span data-stu-id="89330-152">They are not.</span></span> <span data-ttu-id="89330-153">名称不能通过大小写来区分。</span><span class="sxs-lookup"><span data-stu-id="89330-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="89330-154">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="89330-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="89330-155">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="89330-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89330-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="89330-156">See Also</span></span>  
 [<span data-ttu-id="89330-157">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="89330-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="89330-158">命名规则</span><span class="sxs-lookup"><span data-stu-id="89330-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
