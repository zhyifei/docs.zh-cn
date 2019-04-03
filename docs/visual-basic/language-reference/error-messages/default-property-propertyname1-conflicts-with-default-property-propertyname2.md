---
title: 默认属性“<propertyname1>”与“<propertyname2>”中的默认属性“<classname>”冲突，因此应声明为“Shadows”
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: ab45278b2e1199282e3066c34828b9bda716e162
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813166"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="1749d-102">默认属性\<propertyname1 > 与默认属性冲突\<propertyname2 > 中\<类名 >'，因此应声明为 Shadows</span><span class="sxs-lookup"><span data-stu-id="1749d-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>
<span data-ttu-id="1749d-103">使用与基类中定义的属性相同的名称声明属性。</span><span class="sxs-lookup"><span data-stu-id="1749d-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="1749d-104">在这种情况下，在此类的属性应隐藏基类属性。</span><span class="sxs-lookup"><span data-stu-id="1749d-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="1749d-105">此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="1749d-105">This message is a warning.</span></span> <span data-ttu-id="1749d-106">默认假定`Shadows` 。</span><span class="sxs-lookup"><span data-stu-id="1749d-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="1749d-107">若要深入了解如何隐藏警告或将警告视为错误，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="1749d-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1749d-108">**错误 ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="1749d-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1749d-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1749d-109">To correct this error</span></span>  
  
-   <span data-ttu-id="1749d-110">添加`Shadows`关键字为声明或将更改正在声明的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="1749d-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1749d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1749d-111">See also</span></span>

- [<span data-ttu-id="1749d-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="1749d-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="1749d-113">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="1749d-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
