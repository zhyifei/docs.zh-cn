---
title: 대/소문자 표기법
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8af4a15e1e5b34c38b14c6b547cf44801bbf13e6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741769"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="4cd68-102">대/소문자 표기법</span><span class="sxs-lookup"><span data-stu-id="4cd68-102">Capitalization Conventions</span></span>
<span data-ttu-id="4cd68-103">本章中的准则列出了一种针对用例的简单方法，当统一应用此方法时，可以使类型、成员和参数的标识符易于阅读。</span><span class="sxs-lookup"><span data-stu-id="4cd68-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="4cd68-104">标识符的大小写规则</span><span class="sxs-lookup"><span data-stu-id="4cd68-104">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="4cd68-105">若要区分标识符中的单词，请将标识符中每个单词的首字母大写。</span><span class="sxs-lookup"><span data-stu-id="4cd68-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="4cd68-106">不要使用下划线来区分单词，也不要为此在标识符中的任何位置使用下划线。</span><span class="sxs-lookup"><span data-stu-id="4cd68-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="4cd68-107">根据标识符的使用情况，可以通过两种适当的方法将标识符大写：</span><span class="sxs-lookup"><span data-stu-id="4cd68-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="4cd68-108">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="4cd68-108">PascalCasing</span></span>

- <span data-ttu-id="4cd68-109">camelCasing</span><span class="sxs-lookup"><span data-stu-id="4cd68-109">camelCasing</span></span>

 <span data-ttu-id="4cd68-110">PascalCasing 约定用于除参数名称之外的所有标识符，将每个单词的第一个字符大写（包括超过两个字母的首字母缩写），如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="4cd68-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="4cd68-111">这里有一种特殊情况，即遇到两个字母的首字母缩略词时，两个字母都要大写，如下面的标识符所示：</span><span class="sxs-lookup"><span data-stu-id="4cd68-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="4cd68-112">camelCasing 约定仅用于参数名称，将除第一个单词之外的每个单词的第一个字符大写，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="4cd68-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="4cd68-113">该示例还显示，以 camelCasing 标识符开始的双字母缩写词都是小写的。</span><span class="sxs-lookup"><span data-stu-id="4cd68-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="4cd68-114">✔️对于包含多个单词的所有公共成员、类型和命名空间名称，请使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="4cd68-114">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="4cd68-115">✔️使用 camelCasing 作为参数名称。</span><span class="sxs-lookup"><span data-stu-id="4cd68-115">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="4cd68-116">下表描述了不同类型的标识符的大小写规则。</span><span class="sxs-lookup"><span data-stu-id="4cd68-116">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="4cd68-117">식별자</span><span class="sxs-lookup"><span data-stu-id="4cd68-117">Identifier</span></span>|<span data-ttu-id="4cd68-118">Camel</span><span class="sxs-lookup"><span data-stu-id="4cd68-118">Casing</span></span>|<span data-ttu-id="4cd68-119">示例</span><span class="sxs-lookup"><span data-stu-id="4cd68-119">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="4cd68-120">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4cd68-120">Namespace</span></span>|<span data-ttu-id="4cd68-121">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-121">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="4cd68-122">형식</span><span class="sxs-lookup"><span data-stu-id="4cd68-122">Type</span></span>|<span data-ttu-id="4cd68-123">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-123">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="4cd68-124">인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cd68-124">Interface</span></span>|<span data-ttu-id="4cd68-125">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-125">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="4cd68-126">메서드</span><span class="sxs-lookup"><span data-stu-id="4cd68-126">Method</span></span>|<span data-ttu-id="4cd68-127">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="4cd68-128">속성</span><span class="sxs-lookup"><span data-stu-id="4cd68-128">Property</span></span>|<span data-ttu-id="4cd68-129">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="4cd68-130">Event</span><span class="sxs-lookup"><span data-stu-id="4cd68-130">Event</span></span>|<span data-ttu-id="4cd68-131">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="4cd68-132">필드</span><span class="sxs-lookup"><span data-stu-id="4cd68-132">Field</span></span>|<span data-ttu-id="4cd68-133">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="4cd68-134">枚举值</span><span class="sxs-lookup"><span data-stu-id="4cd68-134">Enum value</span></span>|<span data-ttu-id="4cd68-135">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="4cd68-136">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cd68-136">Parameter</span></span>|<span data-ttu-id="4cd68-137">大小</span><span class="sxs-lookup"><span data-stu-id="4cd68-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="4cd68-138">复合词和常用术语的大写</span><span class="sxs-lookup"><span data-stu-id="4cd68-138">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="4cd68-139">出于大写的目的，大多数复合词被视为单个词。</span><span class="sxs-lookup"><span data-stu-id="4cd68-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="4cd68-140">❌ 不要将所谓的 "封闭格式" 组合词中的每个词大写。</span><span class="sxs-lookup"><span data-stu-id="4cd68-140">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="4cd68-141">下面是以单个单词形式拼写的复合词，例如 endpoint。</span><span class="sxs-lookup"><span data-stu-id="4cd68-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="4cd68-142">根据大小写准则，请将封闭形式的复合词视为单个单词。</span><span class="sxs-lookup"><span data-stu-id="4cd68-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="4cd68-143">请使用最新字典确定复合词是否以封闭形式拼写。</span><span class="sxs-lookup"><span data-stu-id="4cd68-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="4cd68-144">形式</span><span class="sxs-lookup"><span data-stu-id="4cd68-144">Pascal</span></span>|<span data-ttu-id="4cd68-145">大小</span><span class="sxs-lookup"><span data-stu-id="4cd68-145">Camel</span></span>|<span data-ttu-id="4cd68-146">not</span><span class="sxs-lookup"><span data-stu-id="4cd68-146">Not</span></span>|
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

## <a name="case-sensitivity"></a><span data-ttu-id="4cd68-147">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="4cd68-147">Case Sensitivity</span></span>
 <span data-ttu-id="4cd68-148">可以在 CLR 上运行的语言不要求区分大小写，尽管有些语言要求。</span><span class="sxs-lookup"><span data-stu-id="4cd68-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="4cd68-149">即使你的语言支持该功能，其他可能访问你的框架的语言也可能不支持。</span><span class="sxs-lookup"><span data-stu-id="4cd68-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="4cd68-150">因此，任何可从外部访问的 API 都不能仅依赖于大小写来区分同一上下文中的两个名称。</span><span class="sxs-lookup"><span data-stu-id="4cd68-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="4cd68-151">❌ 不假定所有编程语言都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="4cd68-151">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="4cd68-152">그러나 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd68-152">They are not.</span></span> <span data-ttu-id="4cd68-153">名称不能仅通过大小写来区分。</span><span class="sxs-lookup"><span data-stu-id="4cd68-153">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="4cd68-154">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="4cd68-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4cd68-155">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4cd68-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4cd68-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cd68-156">See also</span></span>

- [<span data-ttu-id="4cd68-157">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4cd68-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="4cd68-158">명명 지침</span><span class="sxs-lookup"><span data-stu-id="4cd68-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
