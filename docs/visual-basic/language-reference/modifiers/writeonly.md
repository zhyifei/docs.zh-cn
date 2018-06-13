---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 4f34f7f4ada3f8d61c9d855eab1b8b073a3d5ed8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599198"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
指定可写入但无法读取属性。  
  
## <a name="remarks"></a>备注  
  
## <a name="rules"></a>规则  
 **声明上下文。** 只能在模块级别使用 `WriteOnly`。 这意味着的声明上下文`WriteOnly`属性必须是类、 结构或模块，并且不能是源文件、 命名空间或过程。  
  
 你可以将属性声明为`WriteOnly`，但不是变量。  
  
## <a name="when-to-use-writeonly"></a>何时使用 WriteOnly  
 有时你想使用的代码，若要能够设置一个值，但不是会发现它是什么。 例如，敏感数据，如身份证号或密码，需要访问从受未设置任何组件。 在这些情况下，你可以使用`WriteOnly`属性来设置的值。  
  
> [!IMPORTANT]
>  当你定义并使用`WriteOnly`属性，请考虑以下其他保护措施：  
  
-   **重写。** 如果属性是类的成员，允许它默认为[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)，并不声明它`Overridable`或`MustOverride`。 这可以防止使不需要的访问通过重写派生的类。  
  
-   **访问级别。** 如果该属性的敏感数据保存在一个或多个变量时，将其声明[私有](../../../visual-basic/language-reference/modifiers/private.md)以便没有其他代码可以访问它们。  
  
-   **加密。** 将所有的敏感数据存储在加密形式而不是以纯文本。 如果由于某种原因，恶意代码可以访问该内存区域的会更加困难，以便使用的数据。 加密也是很有用，如有必要进行序列化的敏感数据。  
  
-   **重置。** 类、 结构或定义属性的模块正在终止时，重置的敏感数据，为默认值或其他无意义的值。 该内存区域的释放的常规访问权限时，这会提供额外的保护。  
  
-   **持久性。** 如果您可以避免使用它，则不保留任何敏感数据，例如，磁盘上。 此外，请不写入任何敏感数据到剪贴板。  
  
 `WriteOnly`修饰符可用于在此上下文中：  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>请参阅  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)
