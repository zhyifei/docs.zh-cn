---
title: 默认属性 &#39;&lt;propertyname1&gt;&#39; 与默认属性 &#39; 冲突&lt;propertyname2&gt;&#39; 在 &#39;&lt;类名&gt;&#39;，因此应声明为 &#39;阴影 &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af92c06f6d07b6ea64a05b9043547a46e3679111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="7e629-102">默认属性 &#39;&lt;propertyname1&gt;&#39; 与默认属性 &#39; 冲突&lt;propertyname2&gt;&#39; 在 &#39;&lt;类名&gt;&#39;，因此应声明为 &#39;阴影 &#39;</span><span class="sxs-lookup"><span data-stu-id="7e629-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="7e629-103">使用与基类中定义的属性相同的名称声明属性。</span><span class="sxs-lookup"><span data-stu-id="7e629-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="7e629-104">在此情况下，此类中的属性应隐藏基类属性。</span><span class="sxs-lookup"><span data-stu-id="7e629-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="7e629-105">此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="7e629-105">This message is a warning.</span></span> <span data-ttu-id="7e629-106">默认假定`Shadows` 。</span><span class="sxs-lookup"><span data-stu-id="7e629-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="7e629-107">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="7e629-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="7e629-108">**错误 ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="7e629-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e629-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7e629-109">To correct this error</span></span>  
  
-   <span data-ttu-id="7e629-110">添加`Shadows`关键字为声明或将更改正在声明的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="7e629-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e629-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e629-111">See Also</span></span>  
 [<span data-ttu-id="7e629-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="7e629-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="7e629-113">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="7e629-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
