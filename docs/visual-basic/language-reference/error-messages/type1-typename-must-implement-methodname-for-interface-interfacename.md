---
title: <type1>“<typename>”必须为接口“<interfacename>”实现“<methodname>”
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591595"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<type1 > "\<typename >" 必须为接口 "\<interfacename >" 实现 "2methodname @no__t"
类或结构声明实现接口，但不实现由接口定义的过程。 必须实现接口的每个成员。  
  
 **错误 ID：** BC30149  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 使用在接口中定义的相同名称和签名声明过程。 请确保至少包含 `End Function` 或 @no__t。  
  
2. 将 `Implements` 子句添加到 @no__t 或 @no__t 语句的末尾。 例如：  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>请参阅

- [Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)
- [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
