---
title: "默认属性&lt;propertyname1&gt;与默认属性冲突&lt;propertyname2&gt;in&lt;classname&gt;，因此应声明为 Shadows |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
dev_langs:
- VB
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6eac9e0fdc468e27afac82a8a7c9b2251a8f7317
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="077ae-102">默认属性&lt;propertyname1&gt;与默认属性冲突&lt;propertyname2&gt;in&lt;classname&gt;，因此应声明为 Shadows</span><span class="sxs-lookup"><span data-stu-id="077ae-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="077ae-103">使用与基类中定义的属性相同的名称所声明的属性。</span><span class="sxs-lookup"><span data-stu-id="077ae-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="077ae-104">在这种情况下，此类中的属性应隐藏基类属性。</span><span class="sxs-lookup"><span data-stu-id="077ae-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="077ae-105">此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="077ae-105">This message is a warning.</span></span> <span data-ttu-id="077ae-106">`Shadows`默认情况下，则假定。</span><span class="sxs-lookup"><span data-stu-id="077ae-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="077ae-107">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="077ae-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="077ae-108">**错误 ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="077ae-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="077ae-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="077ae-109">To correct this error</span></span>  
  
-   <span data-ttu-id="077ae-110">添加`Shadows`关键字来声明中或更改所声明的属性名称。</span><span class="sxs-lookup"><span data-stu-id="077ae-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="077ae-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="077ae-111">See Also</span></span>  
 <span data-ttu-id="077ae-112">[阴影](../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="077ae-112">[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="077ae-113"> [Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span><span class="sxs-lookup"><span data-stu-id="077ae-113"> [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span></span>
