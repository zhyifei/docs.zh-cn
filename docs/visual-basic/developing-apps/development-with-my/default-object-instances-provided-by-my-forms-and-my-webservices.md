---
title: My.Forms 和 My.WebServices 提供的默认对象实例 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 421995684201ec48d5e8aff9b0ed7640efd1e4b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582651"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>My.Forms 和 My.WebServices 提供的默认对象实例 (Visual Basic)
[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)和[My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)对象提供到窗体、 数据源和应用程序使用的 XML Web 服务的访问权限。 它们执行此操作通过提供的集合*默认实例*的每个对象。  
  
## <a name="default-instances"></a>默认实例  
 默认实例是由运行时提供，不需要为的类声明并实例化使用`Dim`和`New`语句。 下面的示例演示如何你可能会声明并实例化的实例<xref:System.Windows.Forms.Form>类调用`Form1`，以及如何你现在能够获取的默认实例<xref:System.Windows.Forms.Form>类通过`My.Forms`。  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 `My.Forms`对象返回的默认实例的集合，每个`Form`存在于项目中的类。 同样，`My.WebServices`提供在你的应用程序中创建了对引用的每个 Web 服务代理类的默认实例。  
  
## <a name="see-also"></a>请参阅  
 [My.Forms 对象](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.WebServices 对象](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [My 对项目类型的依赖方式](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
