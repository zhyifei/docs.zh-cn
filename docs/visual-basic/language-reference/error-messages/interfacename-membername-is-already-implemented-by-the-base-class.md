---
title: '&#39;&lt;interfacename&gt;。&lt;membername&gt; &#39;已经实现的基类&#39; &lt;n a m e&gt;&#39;。 重新实现&lt;类型&gt;假定'
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 9054c293ede9db4637f23579407f2f76db29f2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588965"
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="36a31-103">&#39;&lt;interfacename&gt;。&lt;membername&gt; &#39;已经实现的基类&#39; &lt;n a m e&gt;&#39;。</span><span class="sxs-lookup"><span data-stu-id="36a31-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="36a31-104">重新实现&lt;类型&gt;假定</span><span class="sxs-lookup"><span data-stu-id="36a31-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="36a31-105">属性、 过程或派生类中的事件使用`Implements`子句，用于指定已在基类中实现的接口成员。</span><span class="sxs-lookup"><span data-stu-id="36a31-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="36a31-106">派生类可以重新实现由其基类实现的接口成员。</span><span class="sxs-lookup"><span data-stu-id="36a31-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="36a31-107">这与重写基类实现不同。</span><span class="sxs-lookup"><span data-stu-id="36a31-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="36a31-108">有关详细信息，请参阅[实现](../../../visual-basic/language-reference/statements/implements-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="36a31-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="36a31-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="36a31-109">By default, this message is a warning.</span></span> <span data-ttu-id="36a31-110">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="36a31-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="36a31-111">**错误 ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="36a31-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="36a31-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="36a31-112">To correct this error</span></span>  
  
-   <span data-ttu-id="36a31-113">如果要重新实现接口成员，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="36a31-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="36a31-114">在派生类中的代码可访问重新实现的成员，除非你使用`MyBase`关键字访问基类实现。</span><span class="sxs-lookup"><span data-stu-id="36a31-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="36a31-115">如果不打算重新实现接口成员，请从属性、过程或事件声明中删除 `Implements` 子句。</span><span class="sxs-lookup"><span data-stu-id="36a31-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a31-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="36a31-116">See Also</span></span>  
 [<span data-ttu-id="36a31-117">接口</span><span class="sxs-lookup"><span data-stu-id="36a31-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
