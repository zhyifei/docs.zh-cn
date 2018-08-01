---
title: 类型成员的名称
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25fe93b63c518f54ee72300f26dfcb3f3ad21d76
ms.sourcegitcommit: b6baf91310f6867223f0f32d596b451592b917b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "33575344"
---
# <a name="names-of-type-members"></a><span data-ttu-id="c272c-102">类型成员的名称</span><span class="sxs-lookup"><span data-stu-id="c272c-102">Names of Type Members</span></span>
<span data-ttu-id="c272c-103">类型由以下成员构成：方法、属性、事件、构造函数和字段。</span><span class="sxs-lookup"><span data-stu-id="c272c-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="c272c-104">以下各节介绍命名类型成员的准则。</span><span class="sxs-lookup"><span data-stu-id="c272c-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="c272c-105">方法的名称</span><span class="sxs-lookup"><span data-stu-id="c272c-105">Names of Methods</span></span>  
 <span data-ttu-id="c272c-106">方法是执行操作的方式，设计准则要求方法名称为谓词或谓词短语。</span><span class="sxs-lookup"><span data-stu-id="c272c-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="c272c-107">遵循此准则，还有利于区分方法名称与属性和类型名称，后者为名词或形容词性短语。</span><span class="sxs-lookup"><span data-stu-id="c272c-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="c272c-108">**✓ DO** 用谓词或谓词短语为方法命名。</span><span class="sxs-lookup"><span data-stu-id="c272c-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="c272c-109">属性的名称</span><span class="sxs-lookup"><span data-stu-id="c272c-109">Names of Properties</span></span>  
 <span data-ttu-id="c272c-110">与其他成员不同，应向属性给定名词性短语或形容词性名称。</span><span class="sxs-lookup"><span data-stu-id="c272c-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="c272c-111">这是因为属性是指数据，属性的名称应反映这一点。</span><span class="sxs-lookup"><span data-stu-id="c272c-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="c272c-112">属性名称总是采用帕斯卡大小写。</span><span class="sxs-lookup"><span data-stu-id="c272c-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="c272c-113">**✓ DO** 使用名词、名词性短语或形容词为属性命名。</span><span class="sxs-lookup"><span data-stu-id="c272c-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="c272c-114">**X DO NOT** 拥有与“Get”方法同名的属性，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c272c-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="c272c-115">此模式通常意味着该属性事实上是一种方法。</span><span class="sxs-lookup"><span data-stu-id="c272c-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="c272c-116">**✓ DO** 用描述集合中项目的复数短语（而不是使用单数短语后接“List”或“Collection”）为集合属性命名。</span><span class="sxs-lookup"><span data-stu-id="c272c-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="c272c-117">**✓ DO** 用肯定性短语（`CanSeek` 而非 `CantSeek`）为布尔属性命名。</span><span class="sxs-lookup"><span data-stu-id="c272c-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="c272c-118">还可选择为布尔属性添加“Is”、“Can”或“Has”，但仅在可带来益处时这么做。</span><span class="sxs-lookup"><span data-stu-id="c272c-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="c272c-119">**✓ CONSIDER** 为属性提供与其类型相同的名称。</span><span class="sxs-lookup"><span data-stu-id="c272c-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="c272c-120">例如，以下属性可正确获取和设置名为 `Color` 的枚举值，因此属性名为 `Color`：</span><span class="sxs-lookup"><span data-stu-id="c272c-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="c272c-121">事件的名称</span><span class="sxs-lookup"><span data-stu-id="c272c-121">Names of Events</span></span>  
 <span data-ttu-id="c272c-122">事件始终指操作，可以是即将发生的，也可以是已经发生的。</span><span class="sxs-lookup"><span data-stu-id="c272c-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="c272c-123">因此，对于方法，事件用谓词命名，并用谓词时态指示引发事件的时间。</span><span class="sxs-lookup"><span data-stu-id="c272c-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="c272c-124">**✓ DO** 用谓词或谓词短语为事件命名。</span><span class="sxs-lookup"><span data-stu-id="c272c-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="c272c-125">示例包括`Clicked`、`Painting` 和 `DroppedDown`。</span><span class="sxs-lookup"><span data-stu-id="c272c-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="c272c-126">**✓ DO** 使用现在时和过去时，为事件名称赋予之前和之后的概念。</span><span class="sxs-lookup"><span data-stu-id="c272c-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="c272c-127">例如，窗口关闭之前引发的事件称为 `Closing`，窗口关闭之后引发的事件称为 `Closed`。</span><span class="sxs-lookup"><span data-stu-id="c272c-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="c272c-128">**X DO NOT**使用 “Before” 或 “After” 前缀和后缀来指示事件之前或之后。</span><span class="sxs-lookup"><span data-stu-id="c272c-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="c272c-129">应按前述使用现在时态和过去时态。</span><span class="sxs-lookup"><span data-stu-id="c272c-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="c272c-130">**✓ DO**使用 “EventHandler” 后缀来命名事件处理程序（委托，用作事件类型），如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c272c-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="c272c-131">**✓ DO** 在事件处理程序中使用名为 `sender` 和 `e` 的两个参数。</span><span class="sxs-lookup"><span data-stu-id="c272c-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="c272c-132">sender 参数表示引发事件的对象。</span><span class="sxs-lookup"><span data-stu-id="c272c-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="c272c-133">sender 参数的类型通常是 `object`，即使可以使用更具体的类型。</span><span class="sxs-lookup"><span data-stu-id="c272c-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="c272c-134">**✓ DO** 为事件参数类名称添加“EventArgs”后缀。</span><span class="sxs-lookup"><span data-stu-id="c272c-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="c272c-135">字段的名称</span><span class="sxs-lookup"><span data-stu-id="c272c-135">Names of Fields</span></span>  
 <span data-ttu-id="c272c-136">字段命名准则适用于静态公开字段和受保护的字段。</span><span class="sxs-lookup"><span data-stu-id="c272c-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="c272c-137">原则不涉及内部和专用字段，而[成员设计准则](../../../docs/standard/design-guidelines/member.md)不允许使用公开字段或受保护的实例字段。</span><span class="sxs-lookup"><span data-stu-id="c272c-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="c272c-138">**✓ DO**在字段名称中使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="c272c-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="c272c-139">**✓ DO**使用名词、名词短语或形容词来命名字段。</span><span class="sxs-lookup"><span data-stu-id="c272c-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="c272c-140">**X DO NOT**在字段名称中使用前缀。</span><span class="sxs-lookup"><span data-stu-id="c272c-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="c272c-141">例如，不要使用 "g_" 或 "s_" 来指示静态字段。</span><span class="sxs-lookup"><span data-stu-id="c272c-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="c272c-142">*部分版权 © 2005, 2009 Microsoft Corporation。* 保留所有权利。</span><span class="sxs-lookup"><span data-stu-id="c272c-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c272c-143">由 Pearson Education, Inc 许可，转载自 [Framework 设计准则：可重用 .NET 库的约定、惯用法和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日作为 Microsoft Windows 开发系列的一部分发布。</span><span class="sxs-lookup"><span data-stu-id="c272c-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c272c-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="c272c-144">See Also</span></span>  
 [<span data-ttu-id="c272c-145">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="c272c-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="c272c-146">命名规则</span><span class="sxs-lookup"><span data-stu-id="c272c-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
