---
title: My.Forms 和 My.WebServices 提供的默认对象实例 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 9285e88e3dc9fd8b3731416b1c40811188d6a33d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563595"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="dd388-102">My.Forms 和 My.WebServices 提供的默认对象实例 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd388-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="dd388-103">[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)并[My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)对象提供对窗体、 数据源和 XML Web 服务使用你的应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="dd388-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="dd388-104">它们执行此操作的集合，从而*默认实例*的每个对象。</span><span class="sxs-lookup"><span data-stu-id="dd388-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="dd388-105">默认实例</span><span class="sxs-lookup"><span data-stu-id="dd388-105">Default Instances</span></span>  
 <span data-ttu-id="dd388-106">默认实例是由运行时提供，不需要进行的类的实例声明并实例化使用`Dim`和`New`语句。</span><span class="sxs-lookup"><span data-stu-id="dd388-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="dd388-107">下面的示例演示如何必须声明和实例化的实例<xref:System.Windows.Forms.Form>类调用`Form1`，，如何现在能够获得的默认实例<xref:System.Windows.Forms.Form>类通过`My.Forms`。</span><span class="sxs-lookup"><span data-stu-id="dd388-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 <span data-ttu-id="dd388-108">`My.Forms`对象返回的默认实例的集合，每个`Form`在项目中存在的类。</span><span class="sxs-lookup"><span data-stu-id="dd388-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="dd388-109">同样，`My.WebServices`提供你的应用程序中创建了对引用的每个 Web 服务代理类的默认实例。</span><span class="sxs-lookup"><span data-stu-id="dd388-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd388-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd388-110">See also</span></span>
- [<span data-ttu-id="dd388-111">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="dd388-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="dd388-112">My.WebServices 对象</span><span class="sxs-lookup"><span data-stu-id="dd388-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="dd388-113">My 对项目类型的依赖方式</span><span class="sxs-lookup"><span data-stu-id="dd388-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
