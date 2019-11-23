---
title: <type1>“<typename>”必须为接口“<membername>”实现“<interfacename>”
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696893"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1 > "\<typename >" 必须为接口 "\<interfacename >" 实现 "\<成员 >"
"\<typename >" 必须为接口 "\<interfacename >" 实现 "\<成员名称 >"。 实现属性必须具有匹配的 "ReadOnly"/"WriteOnly" 说明符。  
  
 类或结构声明实现接口，但不实现由接口定义的过程、属性或事件。 必须实现接口的每个成员。  
  
 **错误 ID：** BC30154  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 使用在接口中定义的相同名称和签名声明成员。 请确保至少包含 `End Function`、`End Sub`或 `End Property` 语句。  
  
2. 将 `Implements` 子句添加到 `Function`、`Sub`、`Property`或 `Event` 语句的末尾。 例如：  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. 实现属性时，请确保使用与接口定义中相同的方式来使用 `ReadOnly` 或 `WriteOnly`。  
  
4. 实现属性时，请根据需要声明 `Get` 和 `Set` 过程。  
  
## <a name="see-also"></a>另请参阅

- [Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)
- [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
