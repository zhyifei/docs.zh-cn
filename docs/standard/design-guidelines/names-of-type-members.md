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
author: KrzysztofCwalina
ms.openlocfilehash: 264627f49a3d2a083f8f46f23f71e8b34d042c8e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127571"
---
# <a name="names-of-type-members"></a><span data-ttu-id="33d30-102">类型成员的名称</span><span class="sxs-lookup"><span data-stu-id="33d30-102">Names of Type Members</span></span>
<span data-ttu-id="33d30-103">类型的成员包括：方法、属性、事件、构造函数和字段。</span><span class="sxs-lookup"><span data-stu-id="33d30-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="33d30-104">以下各部分介绍各类型成员的命名准则。</span><span class="sxs-lookup"><span data-stu-id="33d30-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="33d30-105">方法的名称</span><span class="sxs-lookup"><span data-stu-id="33d30-105">Names of Methods</span></span>  
 <span data-ttu-id="33d30-106">由于方法是操作执行的途径，所以设计准则要求方法名称是谓词或谓词短语。</span><span class="sxs-lookup"><span data-stu-id="33d30-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="33d30-107">通过遵循这一准则，还可将方法名称与属性和类型名称（即名词或形容词短语）区分开来。</span><span class="sxs-lookup"><span data-stu-id="33d30-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="33d30-108">**✓ 务必**使用谓词或谓词短语作为方法名称。</span><span class="sxs-lookup"><span data-stu-id="33d30-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="33d30-109">属性的名称</span><span class="sxs-lookup"><span data-stu-id="33d30-109">Names of Properties</span></span>  
 <span data-ttu-id="33d30-110">与其他成员不同，属性名称须为名词短语或形容词。</span><span class="sxs-lookup"><span data-stu-id="33d30-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="33d30-111">这是因为属性引用数据，且属性名称反映了这一点。</span><span class="sxs-lookup"><span data-stu-id="33d30-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="33d30-112">应始终为属性名称使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="33d30-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="33d30-113">**✓ 务必**使用名词、名词短语或形容词来命名属性。</span><span class="sxs-lookup"><span data-stu-id="33d30-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="33d30-114">**X 不要**设立与 "Get" 方法名称匹配的属性，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="33d30-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="33d30-115">此模式通常表明该属性实际上应是一种方法。</span><span class="sxs-lookup"><span data-stu-id="33d30-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="33d30-116">**✓ 务必**使用用于描述集合中项目的复数形式短语来命名集合属性，而不是使用后跟 "List" 或 "Collection" 的单数形式短语来命名。 </span><span class="sxs-lookup"><span data-stu-id="33d30-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="33d30-117">**✓ 务必**使用肯定语气的短语（`CanSeek` 而不是 `CantSeek`）来命名布尔型属性。</span><span class="sxs-lookup"><span data-stu-id="33d30-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="33d30-118">或者，还可以为布尔型属性使用前缀 "Is"、"Can" 或 "Has"，但仅在适用时使用。 </span><span class="sxs-lookup"><span data-stu-id="33d30-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="33d30-119">**✓ 考虑**使用属性的类型的名称为属性命名。</span><span class="sxs-lookup"><span data-stu-id="33d30-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="33d30-120">例如，以下属性正确获取并设置了名为 `Color` 的枚举值，因此该属性名为 `Color`：</span><span class="sxs-lookup"><span data-stu-id="33d30-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="33d30-121">事件的名称</span><span class="sxs-lookup"><span data-stu-id="33d30-121">Names of Events</span></span>  
 <span data-ttu-id="33d30-122">事件始终是指某个操作，这个操作可能正在发生，也可能已经发生。</span><span class="sxs-lookup"><span data-stu-id="33d30-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="33d30-123">因此与方法一样，事件用谓词命名，谓词时态用于指示事件引发的时间。 </span><span class="sxs-lookup"><span data-stu-id="33d30-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="33d30-124">**✓ 务必**使用谓词或谓词短语来命名事件。</span><span class="sxs-lookup"><span data-stu-id="33d30-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="33d30-125">示例：`Clicked`、`Painting`、`DroppedDown` 等。</span><span class="sxs-lookup"><span data-stu-id="33d30-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="33d30-126">**✓ 务必**通过使用现在时态和过去时态，让事件名称含有时间先后的概念。</span><span class="sxs-lookup"><span data-stu-id="33d30-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="33d30-127">例如，窗口关闭之前引发的事件称为 `Closing`，窗口关闭之后引发的事件称为 `Closed`。</span><span class="sxs-lookup"><span data-stu-id="33d30-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="33d30-128">X 请勿使用 “Before” 或 “After” 前缀和后缀来指示事件之前或之后。</span><span class="sxs-lookup"><span data-stu-id="33d30-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="33d30-129">应按前述使用现在时态和过去时态。</span><span class="sxs-lookup"><span data-stu-id="33d30-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="33d30-130">✓ 请使用 “EventHandler” 后缀来命名事件处理程序（用作事件类型的委托），如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="33d30-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="33d30-131">**✓ 务必**在事件处理程序中使用两个名为 `sender` 和 `e` 的参数。</span><span class="sxs-lookup"><span data-stu-id="33d30-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="33d30-132">sender 参数表示引发事件的对象。</span><span class="sxs-lookup"><span data-stu-id="33d30-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="33d30-133">sender 参数的类型通常是 `object`，且可能会使用更具体的类型。 </span><span class="sxs-lookup"><span data-stu-id="33d30-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="33d30-134">**✓ 务必**使用“EventArgs”后缀来命名事件参数类。 </span><span class="sxs-lookup"><span data-stu-id="33d30-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="33d30-135">字段的名称</span><span class="sxs-lookup"><span data-stu-id="33d30-135">Names of Fields</span></span>  
 <span data-ttu-id="33d30-136">字段命名准则适用于静态公共字段和受保护字段。</span><span class="sxs-lookup"><span data-stu-id="33d30-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="33d30-137">准则不适用于内部字段和专用字段，[成员设计准则](../../../docs/standard/design-guidelines/member.md)不允许使用公共或受保护的实例字段。</span><span class="sxs-lookup"><span data-stu-id="33d30-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="33d30-138"> ✓ 请在字段名称中使用 PascalCasing。  </span><span class="sxs-lookup"><span data-stu-id="33d30-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="33d30-139"> ✓ 请使用名词、名词短语或形容词来命名字段。  </span><span class="sxs-lookup"><span data-stu-id="33d30-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="33d30-140"> X 请勿在字段名称中使用前缀。  </span><span class="sxs-lookup"><span data-stu-id="33d30-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="33d30-141">例如，不要使用 "g_" 或 "s_" 来指示静态字段。</span><span class="sxs-lookup"><span data-stu-id="33d30-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="33d30-142">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="33d30-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="33d30-143">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="33d30-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d30-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="33d30-144">See also</span></span>

- [<span data-ttu-id="33d30-145">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="33d30-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="33d30-146">命名规则</span><span class="sxs-lookup"><span data-stu-id="33d30-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
