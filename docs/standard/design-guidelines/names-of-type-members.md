---
title: "类型成员的名称"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d489d4cf61adfe8550bd16b85cd658e0d545c861
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="names-of-type-members"></a><span data-ttu-id="5c7d8-102">类型成员的名称</span><span class="sxs-lookup"><span data-stu-id="5c7d8-102">Names of Type Members</span></span>
<span data-ttu-id="5c7d8-103">类型由的成员： 方法、 属性、 事件、 构造函数和字段。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="5c7d8-104">以下各节描述了命名类型成员的准则。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="5c7d8-105">方法名称</span><span class="sxs-lookup"><span data-stu-id="5c7d8-105">Names of Methods</span></span>  
 <span data-ttu-id="5c7d8-106">由于方法的执行操作的方法，但设计准则要求方法名称是谓词或谓词短语。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="5c7d8-107">也遵循这一准则选项可用于将方法名称区分开来的属性和类型名称，它们是名词或形容词短语。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="5c7d8-108">**✓ 执行**谓词或谓词短语的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="5c7d8-109">属性名称</span><span class="sxs-lookup"><span data-stu-id="5c7d8-109">Names of Properties</span></span>  
 <span data-ttu-id="5c7d8-110">与其他成员不同属性应为名词短语或形容词名称。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="5c7d8-111">这是因为属性指数据，并且属性的名称将反映出的。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="5c7d8-112">PascalCasing 始终用于属性名称。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="5c7d8-113">**✓ 执行**用名词、 名词短语或形容词命名属性。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="5c7d8-114">**X 不**具有一些属性，如以下示例所示的"Get"方法的名称匹配：</span><span class="sxs-lookup"><span data-stu-id="5c7d8-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="5c7d8-115">此模式通常指示该属性应实际上是一种方法。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="5c7d8-116">**✓ 执行**具有描述而不是使用单数短语跟"列表"或"集合"。 集合中的项的复数形式短语名称集合属性</span><span class="sxs-lookup"><span data-stu-id="5c7d8-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="5c7d8-117">**✓ 执行**名称与赞成短语的布尔型属性 (`CanSeek`而不是`CantSeek`)。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="5c7d8-118">（可选） 还前缀布尔型属性使用"Is"，"可以"或"具有，"但仅在它增添价值。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="5c7d8-119">**请考虑 ✓**指定相同的名称作为其类型的属性。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="5c7d8-120">例如，以下属性正确获取和设置名为枚举值`Color`，因此该属性名为`Color`:</span><span class="sxs-lookup"><span data-stu-id="5c7d8-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="5c7d8-121">事件的名称</span><span class="sxs-lookup"><span data-stu-id="5c7d8-121">Names of Events</span></span>  
 <span data-ttu-id="5c7d8-122">始终引用某一操作，是指位于发生或一个已发生事件。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="5c7d8-123">因此，与方法一样，事件名称中带有谓词，并且谓词时态用于指示何时引发事件的时间。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="5c7d8-124">**✓ 执行**命名事件的谓词或谓词短语。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="5c7d8-125">示例包括`Clicked`， `Painting`， `DroppedDown`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="5c7d8-126">**✓ 执行**为提供了事件名称的概念与之前和之后，使用现在时或过去时态。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="5c7d8-127">例如，将调用关闭窗口之前引发的关闭事件`Closing`，并将调用其中一个时段结束后引发`Closed`。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="5c7d8-128">**X 不**使用"Before"或"After"前缀或 postfixes 以指示预和后期事件。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="5c7d8-129">使用存在和过去时态如上所述。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="5c7d8-130">**✓ 执行**具有"EventHandler"后缀，名称事件处理程序 （委托用作事件类型），如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="5c7d8-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="5c7d8-131">**✓ 执行**使用两个参数名为`sender`和`e`在事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="5c7d8-132">发件人参数表示引发事件的对象。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="5c7d8-133">发件人参数的类型通常是`object`，即使它也可使用更具体的类型。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="5c7d8-134">**✓ 执行**命名自变量类与"EventArgs"后缀的事件。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="5c7d8-135">字段的名称</span><span class="sxs-lookup"><span data-stu-id="5c7d8-135">Names of Fields</span></span>  
 <span data-ttu-id="5c7d8-136">字段命名准则适用于静态的公共和受保护字段。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="5c7d8-137">内部和私有字段未涵盖的准则，和公共或受保护的实例字段都不允许的[成员设计准则](../../../docs/standard/design-guidelines/member.md)。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="5c7d8-138">**✓ 执行**在字段名称中使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="5c7d8-139">**✓ 执行**命名字段使用名词、 名词短语或形容词。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="5c7d8-140">**X 不**字段名称中使用前缀。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="5c7d8-141">例如，不要使用"g_"或"s_"以指示静态字段。</span><span class="sxs-lookup"><span data-stu-id="5c7d8-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="5c7d8-142">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="5c7d8-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5c7d8-143">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="5c7d8-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7d8-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c7d8-144">See Also</span></span>  
 [<span data-ttu-id="5c7d8-145">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="5c7d8-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="5c7d8-146">命名规则</span><span class="sxs-lookup"><span data-stu-id="5c7d8-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
