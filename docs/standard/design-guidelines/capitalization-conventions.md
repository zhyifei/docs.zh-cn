---
title: 大写约定
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
ms.openlocfilehash: 070fc69728c2cb38e465dab9f6f591a77a857531
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46531567"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="cdc98-102">大写约定</span><span class="sxs-lookup"><span data-stu-id="cdc98-102">Capitalization Conventions</span></span>
<span data-ttu-id="cdc98-103">本章中的准则列出了一种针对用例的简单方法，当统一应用此方法时，可以使类型、成员和参数的标识符易于阅读。</span><span class="sxs-lookup"><span data-stu-id="cdc98-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="cdc98-104">标识符的大小写规则</span><span class="sxs-lookup"><span data-stu-id="cdc98-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="cdc98-105">若要区分标识符中的单词，请将标识符中每个单词的首字母大写。</span><span class="sxs-lookup"><span data-stu-id="cdc98-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="cdc98-106">不要使用下划线来区分单词，也不要为此在标识符中的任何位置使用下划线。</span><span class="sxs-lookup"><span data-stu-id="cdc98-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="cdc98-107">根据标识符的使用情况，可以通过两种适当的方法将标识符大写：</span><span class="sxs-lookup"><span data-stu-id="cdc98-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
-   <span data-ttu-id="cdc98-108">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="cdc98-108">PascalCasing</span></span>  
  
-   <span data-ttu-id="cdc98-109">camelCasing</span><span class="sxs-lookup"><span data-stu-id="cdc98-109">camelCasing</span></span>  
  
 <span data-ttu-id="cdc98-110">PascalCasing 约定用于除参数名称之外的所有标识符，将每个单词的第一个字符大写（包括超过两个字母的首字母缩写），如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="cdc98-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="cdc98-111">这里有一种特殊情况，即遇到两个字母的首字母缩略词时，两个字母都要大写，如下面的标识符所示：</span><span class="sxs-lookup"><span data-stu-id="cdc98-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="cdc98-112">camelCasing 约定仅用于参数名称，将除第一个单词之外的每个单词的第一个字符大写，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="cdc98-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="cdc98-113">该示例还显示，以 camelCasing 标识符开始的双字母缩写词都是小写的。</span><span class="sxs-lookup"><span data-stu-id="cdc98-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="cdc98-114">**✓ 请** 将 PascalCasing 用于包含多个单词的所有公共成员、类型和命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="cdc98-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="cdc98-115">**✓ 请** 将 camelCasing 用于参数名称。</span><span class="sxs-lookup"><span data-stu-id="cdc98-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="cdc98-116">下表介绍了不同类型的标识符的大小写规则。</span><span class="sxs-lookup"><span data-stu-id="cdc98-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="cdc98-117">标识符</span><span class="sxs-lookup"><span data-stu-id="cdc98-117">Identifier</span></span>|<span data-ttu-id="cdc98-118">大小写</span><span class="sxs-lookup"><span data-stu-id="cdc98-118">Casing</span></span>|<span data-ttu-id="cdc98-119">示例</span><span class="sxs-lookup"><span data-stu-id="cdc98-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="cdc98-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="cdc98-120">Namespace</span></span>|<span data-ttu-id="cdc98-121">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="cdc98-122">类型</span><span class="sxs-lookup"><span data-stu-id="cdc98-122">Type</span></span>|<span data-ttu-id="cdc98-123">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="cdc98-124">接口</span><span class="sxs-lookup"><span data-stu-id="cdc98-124">Interface</span></span>|<span data-ttu-id="cdc98-125">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="cdc98-126">方法</span><span class="sxs-lookup"><span data-stu-id="cdc98-126">Method</span></span>|<span data-ttu-id="cdc98-127">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="cdc98-128">属性</span><span class="sxs-lookup"><span data-stu-id="cdc98-128">Property</span></span>|<span data-ttu-id="cdc98-129">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="cdc98-130">事件</span><span class="sxs-lookup"><span data-stu-id="cdc98-130">Event</span></span>|<span data-ttu-id="cdc98-131">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="cdc98-132">字段</span><span class="sxs-lookup"><span data-stu-id="cdc98-132">Field</span></span>|<span data-ttu-id="cdc98-133">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="cdc98-134">枚举值</span><span class="sxs-lookup"><span data-stu-id="cdc98-134">Enum value</span></span>|<span data-ttu-id="cdc98-135">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="cdc98-136">参数</span><span class="sxs-lookup"><span data-stu-id="cdc98-136">Parameter</span></span>|<span data-ttu-id="cdc98-137">Camel</span><span class="sxs-lookup"><span data-stu-id="cdc98-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="cdc98-138">复合词和常用术语的大写</span><span class="sxs-lookup"><span data-stu-id="cdc98-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="cdc98-139">出于大写的目的，大多数复合词被视为单个词。</span><span class="sxs-lookup"><span data-stu-id="cdc98-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="cdc98-140">**X DO NOT要** 将所谓封闭形式的复合词中的每个单词大写。</span><span class="sxs-lookup"><span data-stu-id="cdc98-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="cdc98-141">下面是以单个单词形式拼写的复合词，例如 endpoint。</span><span class="sxs-lookup"><span data-stu-id="cdc98-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="cdc98-142">根据大小写准则，请将封闭形式的复合词视为单个单词。</span><span class="sxs-lookup"><span data-stu-id="cdc98-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="cdc98-143">请使用最新字典确定复合词是否以封闭形式拼写。</span><span class="sxs-lookup"><span data-stu-id="cdc98-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="cdc98-144">帕斯卡命名法</span><span class="sxs-lookup"><span data-stu-id="cdc98-144">Pascal</span></span>|<span data-ttu-id="cdc98-145">Camel</span><span class="sxs-lookup"><span data-stu-id="cdc98-145">Camel</span></span>|<span data-ttu-id="cdc98-146">Not</span><span class="sxs-lookup"><span data-stu-id="cdc98-146">Not</span></span>|  
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
  
## <a name="case-sensitivity"></a><span data-ttu-id="cdc98-147">区分大小写</span><span class="sxs-lookup"><span data-stu-id="cdc98-147">Case Sensitivity</span></span>  
 <span data-ttu-id="cdc98-148">可以在 CLR 上运行的语言不要求区分大小写，尽管有些语言要求。</span><span class="sxs-lookup"><span data-stu-id="cdc98-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="cdc98-149">即使你的语言支持该功能，其他可能访问你的框架的语言也可能不支持。</span><span class="sxs-lookup"><span data-stu-id="cdc98-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="cdc98-150">因此，任何可从外部访问的 API 都不能仅依赖于大小写来区分同一上下文中的两个名称。</span><span class="sxs-lookup"><span data-stu-id="cdc98-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="cdc98-151">**X DO NOT要** 假定所有编程语言都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cdc98-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="cdc98-152">它们不是这样的。</span><span class="sxs-lookup"><span data-stu-id="cdc98-152">They are not.</span></span> <span data-ttu-id="cdc98-153">名称不能仅通过大小写来区分。</span><span class="sxs-lookup"><span data-stu-id="cdc98-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="cdc98-154">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="cdc98-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cdc98-155">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="cdc98-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc98-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdc98-156">See also</span></span>

- [<span data-ttu-id="cdc98-157">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="cdc98-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="cdc98-158">命名规则</span><span class="sxs-lookup"><span data-stu-id="cdc98-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
