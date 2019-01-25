---
title: 默认属性&#39; &lt;propertyname1&gt; &#39;默认属性与冲突&#39; &lt;propertyname2&gt; &#39;在&#39; &lt;classname&gt; &#39;，因此应声明&#39;Shadows&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 3099467fa3c5a162c13c9235fb8d55375953ba3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521421"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="01ff1-102">默认属性&#39; &lt;propertyname1&gt; &#39;默认属性与冲突&#39; &lt;propertyname2&gt; &#39;在&#39; &lt;classname&gt; &#39;，因此应声明&#39;Shadows&#39;</span><span class="sxs-lookup"><span data-stu-id="01ff1-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="01ff1-103">使用与基类中定义的属性相同的名称声明属性。</span><span class="sxs-lookup"><span data-stu-id="01ff1-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="01ff1-104">在这种情况下，在此类的属性应隐藏基类属性。</span><span class="sxs-lookup"><span data-stu-id="01ff1-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="01ff1-105">此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="01ff1-105">This message is a warning.</span></span> <span data-ttu-id="01ff1-106">默认假定`Shadows` 。</span><span class="sxs-lookup"><span data-stu-id="01ff1-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="01ff1-107">若要深入了解如何隐藏警告或将警告视为错误，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="01ff1-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="01ff1-108">**错误 ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="01ff1-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01ff1-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="01ff1-109">To correct this error</span></span>  
  
-   <span data-ttu-id="01ff1-110">添加`Shadows`关键字为声明或将更改正在声明的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="01ff1-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ff1-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="01ff1-111">See also</span></span>
- [<span data-ttu-id="01ff1-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="01ff1-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="01ff1-113">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="01ff1-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
