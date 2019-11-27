---
title: My.Forms 和 My.WebServices 提供的默认对象实例
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: d06df4bd023892429b2aaefdd624398a6546d06d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330205"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="f2ebe-102">My.Forms 和 My.WebServices 提供的默认对象实例 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2ebe-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="f2ebe-103">[My. forms](../../../visual-basic/language-reference/objects/my-forms-object.md)和[WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)对象提供对应用程序使用的窗体、数据源和 XML Web services 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f2ebe-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="f2ebe-104">它们通过提供每个对象的*默认实例*集合来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="f2ebe-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="f2ebe-105">默认实例</span><span class="sxs-lookup"><span data-stu-id="f2ebe-105">Default Instances</span></span>  

 <span data-ttu-id="f2ebe-106">默认实例是由运行时提供的类的实例，无需使用 `Dim` 和 `New` 语句进行声明和实例化。</span><span class="sxs-lookup"><span data-stu-id="f2ebe-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="f2ebe-107">下面的示例演示如何声明和实例化名为 `Form1`<xref:System.Windows.Forms.Form> 类的实例，以及你现在如何通过 `My.Forms`获取此 <xref:System.Windows.Forms.Form> 类的默认实例。</span><span class="sxs-lookup"><span data-stu-id="f2ebe-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="f2ebe-108">`My.Forms` 对象将为项目中存在的每个 `Form` 类返回默认实例的集合。</span><span class="sxs-lookup"><span data-stu-id="f2ebe-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="f2ebe-109">同样，`My.WebServices` 为已在应用程序中创建引用的每个 Web 服务提供代理类的默认实例。</span><span class="sxs-lookup"><span data-stu-id="f2ebe-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ebe-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2ebe-110">See also</span></span>

- [<span data-ttu-id="f2ebe-111">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="f2ebe-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="f2ebe-112">My.WebServices 对象</span><span class="sxs-lookup"><span data-stu-id="f2ebe-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="f2ebe-113">My 对项目类型的依赖方式</span><span class="sxs-lookup"><span data-stu-id="f2ebe-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
