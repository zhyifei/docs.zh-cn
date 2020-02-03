---
title: 类型成员的名称
ms.date: 10/22/2008
ms.technology: dotnet-standard
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
ms.openlocfilehash: 81c837bd045992043208a59f6ee16803c1d6eb3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744177"
---
# <a name="names-of-type-members"></a><span data-ttu-id="2827e-102">类型成员的名称</span><span class="sxs-lookup"><span data-stu-id="2827e-102">Names of Type Members</span></span>
<span data-ttu-id="2827e-103">类型的成员包括：方法、属性、事件、构造函数和字段。</span><span class="sxs-lookup"><span data-stu-id="2827e-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="2827e-104">以下各部分介绍各类型成员的命名准则。</span><span class="sxs-lookup"><span data-stu-id="2827e-104">The following sections describe guidelines for naming type members.</span></span>

## <a name="names-of-methods"></a><span data-ttu-id="2827e-105">方法的名称</span><span class="sxs-lookup"><span data-stu-id="2827e-105">Names of Methods</span></span>
 <span data-ttu-id="2827e-106">由于方法是操作执行的途径，所以设计准则要求方法名称是谓词或谓词短语。</span><span class="sxs-lookup"><span data-stu-id="2827e-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="2827e-107">通过遵循这一准则，还可将方法名称与属性和类型名称（即名词或形容词短语）区分开来。</span><span class="sxs-lookup"><span data-stu-id="2827e-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>

 <span data-ttu-id="2827e-108">✔️为谓词或谓词短语指定方法名称。</span><span class="sxs-lookup"><span data-stu-id="2827e-108">✔️ DO give methods names that are verbs or verb phrases.</span></span>

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a><span data-ttu-id="2827e-109">属性的名称</span><span class="sxs-lookup"><span data-stu-id="2827e-109">Names of Properties</span></span>
 <span data-ttu-id="2827e-110">与其他成员不同，属性名称须为名词短语或形容词。</span><span class="sxs-lookup"><span data-stu-id="2827e-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="2827e-111">这是因为属性引用数据，且属性名称反映了这一点。</span><span class="sxs-lookup"><span data-stu-id="2827e-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="2827e-112">应始终为属性名称使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="2827e-112">PascalCasing is always used for property names.</span></span>

 <span data-ttu-id="2827e-113">✔️使用名词、名词短语或形容词名称属性。</span><span class="sxs-lookup"><span data-stu-id="2827e-113">✔️ DO name properties using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="2827e-114">❌ 没有与 "Get" 方法的名称相匹配的属性，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="2827e-114">❌ DO NOT have properties that match the name of "Get" methods as in the following example:</span></span>

 <span data-ttu-id="2827e-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span><span class="sxs-lookup"><span data-stu-id="2827e-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span></span>

 <span data-ttu-id="2827e-116">此模式通常表明该属性实际上应是一种方法。</span><span class="sxs-lookup"><span data-stu-id="2827e-116">This pattern typically indicates that the property should really be a method.</span></span>

 <span data-ttu-id="2827e-117">✔️使用一个复数短语来描述集合中的项，而不是使用后跟 "List" 或 "Collection" 的短语来命名集合属性。</span><span class="sxs-lookup"><span data-stu-id="2827e-117">✔️ DO name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection".</span></span>

 <span data-ttu-id="2827e-118">✔️使用赞成短语（`CanSeek` 而不是 `CantSeek`）命名布尔属性。</span><span class="sxs-lookup"><span data-stu-id="2827e-118">✔️ DO name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="2827e-119">或者，还可以在布尔属性前面添加 "Is"、"Can" 或 "has" 前缀，但前提是在它添加值的位置。</span><span class="sxs-lookup"><span data-stu-id="2827e-119">Optionally, you can also prefix Boolean properties with "Is", "Can", or "Has", but only where it adds value.</span></span>

 <span data-ttu-id="2827e-120">✔️考虑为属性提供与其类型相同的名称。</span><span class="sxs-lookup"><span data-stu-id="2827e-120">✔️ CONSIDER giving a property the same name as its type.</span></span>

 <span data-ttu-id="2827e-121">例如，以下属性可正确获取和设置名为 `Color` 的枚举值，因此属性名为 `Color`：</span><span class="sxs-lookup"><span data-stu-id="2827e-121">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a><span data-ttu-id="2827e-122">事件的名称</span><span class="sxs-lookup"><span data-stu-id="2827e-122">Names of Events</span></span>
 <span data-ttu-id="2827e-123">事件始终是指某个操作，这个操作可能正在发生，也可能已经发生。</span><span class="sxs-lookup"><span data-stu-id="2827e-123">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="2827e-124">因此与方法一样，事件用谓词命名，谓词时态用于指示事件引发的时间。</span><span class="sxs-lookup"><span data-stu-id="2827e-124">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>

 <span data-ttu-id="2827e-125">✔️使用动词或动词短语来命名事件。</span><span class="sxs-lookup"><span data-stu-id="2827e-125">✔️ DO name events with a verb or a verb phrase.</span></span>

 <span data-ttu-id="2827e-126">示例包括`Clicked`、`Painting` 和 `DroppedDown`。</span><span class="sxs-lookup"><span data-stu-id="2827e-126">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>

 <span data-ttu-id="2827e-127">✔️使用现有的和过去的时态为事件名称提供前后的概念。</span><span class="sxs-lookup"><span data-stu-id="2827e-127">✔️ DO give events names with a concept of before and after, using the present and past tenses.</span></span>

 <span data-ttu-id="2827e-128">例如，在窗口关闭前引发的关闭事件可命名为 `Closing`，而在窗口关闭后后引发的关闭事件可命名为 `Closed`。</span><span class="sxs-lookup"><span data-stu-id="2827e-128">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>

 <span data-ttu-id="2827e-129">❌ 不要使用 "Before" 或 "After" 前缀或 postfixes 来指示前和后事件。</span><span class="sxs-lookup"><span data-stu-id="2827e-129">❌ DO NOT use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="2827e-130">应按前述使用现在时态和过去时态。</span><span class="sxs-lookup"><span data-stu-id="2827e-130">Use present and past tenses as just described.</span></span>

 <span data-ttu-id="2827e-131">✔️使用 "EventHandler" 后缀来命名事件处理程序（用作事件类型的委托），如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="2827e-131">✔️ DO name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 <span data-ttu-id="2827e-132">✔️确实使用两个名为 `sender` 的参数，并在事件处理程序中 `e`。</span><span class="sxs-lookup"><span data-stu-id="2827e-132">✔️ DO use two parameters named `sender` and `e` in event handlers.</span></span>

 <span data-ttu-id="2827e-133">sender 参数表示引发事件的对象。</span><span class="sxs-lookup"><span data-stu-id="2827e-133">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="2827e-134">sender 参数的类型通常是 `object`，即使可以使用更具体的类型。</span><span class="sxs-lookup"><span data-stu-id="2827e-134">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>

 <span data-ttu-id="2827e-135">✔️用 "EventArgs" 后缀命名事件参数类。</span><span class="sxs-lookup"><span data-stu-id="2827e-135">✔️ DO name event argument classes with the "EventArgs" suffix.</span></span>

## <a name="names-of-fields"></a><span data-ttu-id="2827e-136">字段的名称</span><span class="sxs-lookup"><span data-stu-id="2827e-136">Names of Fields</span></span>
 <span data-ttu-id="2827e-137">字段命名准则适用于静态公共字段和受保护字段。</span><span class="sxs-lookup"><span data-stu-id="2827e-137">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="2827e-138">原则不涉及内部和专用字段，而[成员设计准则](../../../docs/standard/design-guidelines/member.md)不允许使用公开字段或受保护的实例字段。</span><span class="sxs-lookup"><span data-stu-id="2827e-138">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>

 <span data-ttu-id="2827e-139">✔️在字段名称中使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="2827e-139">✔️ DO use PascalCasing in field names.</span></span>

 <span data-ttu-id="2827e-140">✔️使用名词、名词短语或形容词来命名字段。</span><span class="sxs-lookup"><span data-stu-id="2827e-140">✔️ DO name fields using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="2827e-141">❌ 不使用字段名称前缀。</span><span class="sxs-lookup"><span data-stu-id="2827e-141">❌ DO NOT use a prefix for field names.</span></span>

 <span data-ttu-id="2827e-142">例如，不要使用 "g_" 或 "s_" 来指示静态字段。</span><span class="sxs-lookup"><span data-stu-id="2827e-142">For example, do not use "g_" or "s_" to indicate static fields.</span></span>

 <span data-ttu-id="2827e-143">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="2827e-143">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2827e-144">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="2827e-144">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2827e-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2827e-145">See also</span></span>

- [<span data-ttu-id="2827e-146">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="2827e-146">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="2827e-147">命名规则</span><span class="sxs-lookup"><span data-stu-id="2827e-147">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
