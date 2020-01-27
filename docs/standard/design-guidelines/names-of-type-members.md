---
title: 형식 멤버의 이름
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
# <a name="names-of-type-members"></a><span data-ttu-id="04d39-102">형식 멤버의 이름</span><span class="sxs-lookup"><span data-stu-id="04d39-102">Names of Type Members</span></span>
<span data-ttu-id="04d39-103">형식은 메서드, 속성, 이벤트, 생성자 및 필드 등의 멤버로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="04d39-104">다음 섹션에서는 형식 멤버 이름 지정에 대한 지침을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-104">The following sections describe guidelines for naming type members.</span></span>

## <a name="names-of-methods"></a><span data-ttu-id="04d39-105">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="04d39-105">Names of Methods</span></span>
 <span data-ttu-id="04d39-106">메서드가 작업을 수행하는 수단이기 때문에 디자인 지침에서는 메서드 이름이 동사 또는 동사구여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="04d39-107">또한 이 지침을 따르면 명사 또는 형용사구인 속성 및 형식 이름과 메서드 이름을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>

 <span data-ttu-id="04d39-108">✔️为谓词或谓词短语指定方法名称。</span><span class="sxs-lookup"><span data-stu-id="04d39-108">✔️ DO give methods names that are verbs or verb phrases.</span></span>

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a><span data-ttu-id="04d39-109">속성 이름</span><span class="sxs-lookup"><span data-stu-id="04d39-109">Names of Properties</span></span>
 <span data-ttu-id="04d39-110">다른 멤버와 달리 속성은 명사구 또는 형용사 이름이 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="04d39-111">속성이 데이터를 나타내기 때문에 속성 이름은 이를 반영해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="04d39-112">PascalCasing은 속성 이름에 항상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-112">PascalCasing is always used for property names.</span></span>

 <span data-ttu-id="04d39-113">✔️使用名词、名词短语或形容词名称属性。</span><span class="sxs-lookup"><span data-stu-id="04d39-113">✔️ DO name properties using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="04d39-114">❌ 没有与 "Get" 方法的名称相匹配的属性，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="04d39-114">❌ DO NOT have properties that match the name of "Get" methods as in the following example:</span></span>

 <span data-ttu-id="04d39-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span><span class="sxs-lookup"><span data-stu-id="04d39-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span></span>

 <span data-ttu-id="04d39-116">이 패턴은 일반적으로 속성이 실제로 메서드임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-116">This pattern typically indicates that the property should really be a method.</span></span>

 <span data-ttu-id="04d39-117">✔️使用一个复数短语来描述集合中的项，而不是使用后跟 "List" 或 "Collection" 的短语来命名集合属性。</span><span class="sxs-lookup"><span data-stu-id="04d39-117">✔️ DO name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection".</span></span>

 <span data-ttu-id="04d39-118">✔️使用赞成短语（`CanSeek` 而不是 `CantSeek`）命名布尔属性。</span><span class="sxs-lookup"><span data-stu-id="04d39-118">✔️ DO name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="04d39-119">或者，还可以在布尔属性前面添加 "Is"、"Can" 或 "has" 前缀，但前提是在它添加值的位置。</span><span class="sxs-lookup"><span data-stu-id="04d39-119">Optionally, you can also prefix Boolean properties with "Is", "Can", or "Has", but only where it adds value.</span></span>

 <span data-ttu-id="04d39-120">✔️考虑为属性提供与其类型相同的名称。</span><span class="sxs-lookup"><span data-stu-id="04d39-120">✔️ CONSIDER giving a property the same name as its type.</span></span>

 <span data-ttu-id="04d39-121">예를 들어, 다음 속성은 현재 올바르게 `Color`라는 열거형 값을 설정하므로 속성 이름은 `Color`입니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-121">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a><span data-ttu-id="04d39-122">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="04d39-122">Names of Events</span></span>
 <span data-ttu-id="04d39-123">이벤트는 발생 중인 작업 또는 발생한 작업 중 하나를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-123">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="04d39-124">따라서 메서드와 마찬가지로 이벤트는 동사를 사용하여 명명하고 동사 시제는 이벤트가 발생할 시간을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-124">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>

 <span data-ttu-id="04d39-125">✔️使用动词或动词短语来命名事件。</span><span class="sxs-lookup"><span data-stu-id="04d39-125">✔️ DO name events with a verb or a verb phrase.</span></span>

 <span data-ttu-id="04d39-126">예를 들면 `Clicked`, `Painting`, `DroppedDown` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-126">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>

 <span data-ttu-id="04d39-127">✔️使用现有的和过去的时态为事件名称提供前后的概念。</span><span class="sxs-lookup"><span data-stu-id="04d39-127">✔️ DO give events names with a concept of before and after, using the present and past tenses.</span></span>

 <span data-ttu-id="04d39-128">예를 들어 창이 닫히기 전에 발생하는 닫기 이벤트는 `Closing`이라고 하고 창이 닫힌 후에 발생하는 닫기 이벤트는 `Closed`라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-128">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>

 <span data-ttu-id="04d39-129">❌ 不要使用 "Before" 或 "After" 前缀或 postfixes 来指示前和后事件。</span><span class="sxs-lookup"><span data-stu-id="04d39-129">❌ DO NOT use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="04d39-130">위에서 설명한 대로 현재 및 과거 시제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-130">Use present and past tenses as just described.</span></span>

 <span data-ttu-id="04d39-131">✔️使用 "EventHandler" 后缀来命名事件处理程序（用作事件类型的委托），如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="04d39-131">✔️ DO name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 <span data-ttu-id="04d39-132">✔️确实使用两个名为 `sender` 的参数，并在事件处理程序中 `e`。</span><span class="sxs-lookup"><span data-stu-id="04d39-132">✔️ DO use two parameters named `sender` and `e` in event handlers.</span></span>

 <span data-ttu-id="04d39-133">보낸 사람 매개 변수는 이벤트를 발생시킨 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-133">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="04d39-134">보낸 사람 매개 변수는 보다 구체적인 형식을 적용할 수 있더라도 일반적으로 `object` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-134">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>

 <span data-ttu-id="04d39-135">✔️用 "EventArgs" 后缀命名事件参数类。</span><span class="sxs-lookup"><span data-stu-id="04d39-135">✔️ DO name event argument classes with the "EventArgs" suffix.</span></span>

## <a name="names-of-fields"></a><span data-ttu-id="04d39-136">필드 이름</span><span class="sxs-lookup"><span data-stu-id="04d39-136">Names of Fields</span></span>
 <span data-ttu-id="04d39-137">필드 명명 지침은 공용 및 보호된 고정 필드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-137">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="04d39-138">내부 및 개인 필드는 지침에서 다루지 않고 공용 또는 보호된 인스턴스 필드는 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)에서 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d39-138">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>

 <span data-ttu-id="04d39-139">✔️在字段名称中使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="04d39-139">✔️ DO use PascalCasing in field names.</span></span>

 <span data-ttu-id="04d39-140">✔️使用名词、名词短语或形容词来命名字段。</span><span class="sxs-lookup"><span data-stu-id="04d39-140">✔️ DO name fields using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="04d39-141">❌ 不使用字段名称前缀。</span><span class="sxs-lookup"><span data-stu-id="04d39-141">❌ DO NOT use a prefix for field names.</span></span>

 <span data-ttu-id="04d39-142">예를 들어 "g_" 또는 "s_"를 사용하여 고정 필드를 나타내지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="04d39-142">For example, do not use "g_" or "s_" to indicate static fields.</span></span>

 <span data-ttu-id="04d39-143">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="04d39-143">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="04d39-144">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="04d39-144">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="04d39-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04d39-145">See also</span></span>

- [<span data-ttu-id="04d39-146">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="04d39-146">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="04d39-147">명명 지침</span><span class="sxs-lookup"><span data-stu-id="04d39-147">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
